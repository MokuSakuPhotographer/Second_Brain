<!-- spotify-obsidian:generated:v1 -->
# Spotifyログ

[[Spotifyダッシュボード|Spotifyダッシュボードを開く]]

![[Spotify状態]]

```dataviewjs
const pages = dv.pages('"Spotify/Spotifyログ"').where(p => p.type === "spotify-log" && String(p.date?.toISODate?.() ?? p.date) >= "2026-07-01").sort(p => p.date, "desc");
dv.table(["日付", "再生回数", "推定楽曲時間", "日別ログ"], pages.map(p => {
 const ms = Number(p.estimated_duration_ms) || 0;
 return [p.date, Number(p.play_count) || 0, `${Math.floor(ms / 3600000)}時間${Math.floor(ms / 60000) % 60}分`, p.file.link];
}));
```

データ提供：[Last.fm](https://www.last.fm/) / [powered by AudioScrobbler](https://www.last.fm/)（個人利用）
