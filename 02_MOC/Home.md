# Home

Vault全体のナビゲーション起点です。

## Today's knowridge

```dataviewjs
const excludedFolders = [
  "09_ナレッジベース/地球から1週間かけて酸素が消えたらどうなるか",
  "09_ナレッジベース/wikipedia"
];
const pages = dv.pages('"09_ナレッジベース"')
  .where(p => !excludedFolders.some(folder =>
    p.file.folder === folder || p.file.folder.startsWith(folder + "/")))
  .array()
  .sort((a, b) => a.file.path < b.file.path ? -1 : a.file.path > b.file.path ? 1 : 0);

if (pages.length === 0) {
  dv.paragraph("表示対象の記事がありません。");
} else {
  const today = new Intl.DateTimeFormat("en-CA", {
    timeZone: "Asia/Tokyo", year: "numeric", month: "2-digit", day: "2-digit"
  }).format(new Date());
  let seed = 2166136261;
  for (const char of today) seed = Math.imul(seed ^ char.charCodeAt(0), 16777619);
  seed += 0x6D2B79F5;
  let random = Math.imul(seed ^ (seed >>> 15), seed | 1);
  random ^= random + Math.imul(random ^ (random >>> 7), random | 61);
  random = ((random ^ (random >>> 14)) >>> 0) / 4294967296;
  const article = pages[Math.floor(random * pages.length)];
  dv.paragraph(dv.fileLink(article.file.name));
}
```

## カテゴリ

- [[自己管理・日次 MOC]]
- [[知識 MOC]]
- [[機材・環境 MOC]]
- [[メディア MOC]]
- [[購入・契約 MOC]]
- [[制作・プロジェクト MOC]]
