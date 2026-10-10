<!-- spotify-obsidian:generated:v1 -->
# Spotifyダッシュボード

[[Spotifyログ|日別ログの一覧]]

![[Spotify状態]]

```dataviewjs
// Embedded in the dashboard: no external scripts, network, or chart libraries.
const MusicStats = (() => {
  const normalize = value => String(value ?? "").normalize("NFKC").toLowerCase().replace(/\s+/g, " ").trim();
  const validMs = value => typeof value === "number" && Number.isFinite(value) && value > 0 && value <= 86400000;
  const isoDay = value => {
    const text = typeof value === "string" ? value : value?.toISODate?.();
    return /^\d{4}-\d{2}-\d{2}$/.test(text ?? "") ? text : null;
  };
  function shift(day, delta) {
    const date = new Date(`${day}T00:00:00Z`);
    date.setUTCDate(date.getUTCDate() + delta);
    return date.toISOString().slice(0, 10);
  }
  function ranges(today) {
    const weekday = new Date(`${today}T00:00:00Z`).getUTCDay();
    return [
      {label: "今週", from: shift(today, -((weekday + 6) % 7)), to: today},
      {label: "今月", from: `${today.slice(0, 7)}-01`, to: today},
      {label: "直近3ヶ月（90日）", from: shift(today, -89), to: today},
      {label: "今年", from: `${today.slice(0, 4)}-01-01`, to: today}
    ];
  }
  function aggregate(pages, range) {
    const artists = new Map(), songs = new Map(), genres = new Map(), days = new Map(), ids = new Set();
    let count = 0, ms = 0, unknown = 0, invalid = 0;
    for (let day = range.from; day <= range.to; day = shift(day, 1)) days.set(day, {count: 0, ms: 0});
    const add = (map, key, label) => { const row = map.get(key) ?? {label, count: 0}; row.count++; map.set(key, row); };
    for (const page of pages) {
      const day = isoDay(page.date);
      if (!day || day < range.from || day > range.to) continue;
      const source = page.plays?.array?.() ?? page.plays;
      if (!Array.isArray(source)) { invalid++; continue; }
      for (const play of source) {
        if (!play || typeof play.id !== "string" || !play.track || !play.artist) { invalid++; continue; }
        if (ids.has(play.id)) continue;
        ids.add(play.id);
        count++;
        const duration = validMs(play.duration_ms) ? play.duration_ms : 0;
        ms += duration;
        if (!duration) unknown++;
        const artist = normalize(play.artist);
        const song = JSON.stringify([artist, normalize(play.track), normalize(play.album), normalize(play.mbid)]);
        add(artists, artist, String(play.artist));
        add(songs, song, `${play.track} — ${play.artist}${play.album ? ` / ${play.album}` : ""}`);
        const genre = String(play.primary_genre || "未分類");
        add(genres, normalize(genre), genre);
        const daily = days.get(day); daily.count++; daily.ms += duration;
      }
    }
    const rank = map => {
      const sorted = [...map.values()].sort((a, b) => b.count - a.count || a.label.localeCompare(b.label, "ja"));
      let previous = null, position = 0;
      return sorted.map((row, index) => {
        if (row.count !== previous) position = index + 1;
        previous = row.count;
        return {...row, rank: position, percent: count ? row.count / count * 100 : 0};
      });
    };
    return {count, ms, unknown, invalid, uniqueSongs: songs.size, uniqueArtists: artists.size,
      artists: rank(artists), songs: rank(songs), genres: rank(genres), days: [...days.entries()]};
  }
  const time = ms => `${Math.floor(ms / 3600000)}時間${Math.floor(ms / 60000) % 60}分`;
  return {normalize, ranges, aggregate, time, isoDay};
})();
if (typeof module !== "undefined") module.exports = MusicStats;
if (typeof dv !== "undefined") {
  const root = dv.container;
  const historyFrom = "2026-07-01";
  const pages = dv.pages('"Spotify/Spotifyログ"').where(p => p.type === "spotify-log" && (!/^\d{4}-\d{2}-\d{2}$/.test(historyFrom) || MusicStats.isoDay(p.date) >= historyFrom)).array();
  const today = dv.luxon.DateTime.now().setZone("Asia/Tokyo").toISODate();
  const periods = MusicStats.ranges(today).map(range => ({...range,
    from: /^\d{4}-\d{2}-\d{2}$/.test(historyFrom) && historyFrom > range.from ? historyFrom : range.from}));
  const controls = document.createElement("div");
  controls.style.cssText = "display:flex;gap:8px;flex-wrap:wrap;margin:12px 0";
  root.appendChild(controls);
  const body = document.createElement("div"); root.appendChild(body);
  const el = (tag, text, parent = body) => {
    const element = document.createElement(tag);
    if (text != null) element.textContent = String(text);
    parent.appendChild(element); return element;
  };
  function table(headers, rows) {
    const wrap = el("div"); wrap.style.overflowX = "auto";
    const table = el("table", null, wrap); table.className = "dataview table-view-table";
    const head = el("thead", null, table), tr = el("tr", null, head);
    headers.forEach(h => el("th", h, tr));
    const tbody = el("tbody", null, table);
    rows.forEach(row => { const tr = el("tr", null, tbody); row.forEach(cell => el("td", cell, tr)); });
  }
  function bars(rows, getValue, format, label) {
    el("h4", label);
    const maximum = Math.max(1, ...rows.map(getValue));
    const area = el("div"); area.style.cssText = "max-height:400px;overflow:auto";
    for (const row of rows) {
      const line = el("div", null, area); line.style.cssText = "display:grid;grid-template-columns:105px 1fr 95px;gap:8px;align-items:center;margin:4px 0";
      el("span", row[0], line);
      const background = el("div", null, line); background.style.cssText = "height:12px;background:var(--background-modifier-border);border-radius:3px";
      const fill = el("div", null, background); fill.style.cssText = `height:100%;width:${Math.max(0, getValue(row)) / maximum * 100}%;background:var(--interactive-accent);border-radius:3px`;
      fill.setAttribute("role", "img"); fill.setAttribute("aria-label", `${row[0]} ${format(getValue(row))}`);
      el("span", format(getValue(row)), line);
    }
  }
  function render(index) {
    body.replaceChildren();
    [...controls.children].forEach((button, i) => button.setAttribute("aria-pressed", String(i === index)));
    const range = periods[index], stats = MusicStats.aggregate(pages, range);
    el("h2", range.label); el("p", `${range.from}〜${range.to}（Asia/Tokyo）`);
    table(["再生回数", "推定楽曲時間", "時間不明", "ユニーク楽曲", "ユニークアーティスト"],
      [[stats.count, MusicStats.time(stats.ms), stats.unknown, stats.uniqueSongs, stats.uniqueArtists]]);
    for (const [label, ranking] of [["アーティスト", stats.artists], ["楽曲", stats.songs], ["ジャンル", stats.genres]]) {
      el("h3", `${label}別 TOP10`);
      table(["順位", label, "再生回数"], ranking.slice(0, 10).map(r => [r.rank, r.label, r.count]));
    }
    el("h3", "ジャンル統計");
    table(["ジャンル", "再生回数", "割合"], stats.genres.map(r => [r.label, r.count, `${r.percent.toFixed(1)}%`]));
    el("p", `未分類：${stats.genres.find(r => r.label === "未分類")?.count ?? 0}件`);
    const recentDays = [...stats.days].reverse();
    bars(recentDays, r => r[1].count, v => `${v}回`, "日別再生回数（新しい日付から）");
    bars(recentDays, r => r[1].ms, MusicStats.time, "日別推定楽曲時間（新しい日付から）");
    const details = el("details"), summary = el("summary", "日別の数値", details);
    const old = body; // tables are generated in the body, then moved inside details.
    table(["日付", "再生回数", "推定楽曲時間"], stats.days.map(([day, value]) => [day, value.count, MusicStats.time(value.ms)]));
    details.appendChild(old.lastElementChild);
    if (stats.invalid) el("p", `読み取れなかったデータ：${stats.invalid}件（正常な履歴の集計は継続）`);
    el("p", "推定楽曲時間は取得済みの曲の長さの合計です。実際に聴いた時間とは異なります。同率は競技順位、TOP10は10行まで表示します。");
  }
  periods.forEach((range, index) => {
    const button = document.createElement("button"); button.textContent = range.label;
    button.addEventListener("click", () => render(index)); controls.appendChild(button);
  });
  render(0);
}

```

データ提供：[Last.fm](https://www.last.fm/) / [powered by AudioScrobbler](https://www.last.fm/)（個人利用）
