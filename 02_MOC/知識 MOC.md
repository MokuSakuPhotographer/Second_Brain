# 知識 MOC

[[Home|← Home]]

## 入口

- [[ナレッジベース一覧]]

## 言語

```dataviewjs
const collator = new Intl.Collator("ja", { sensitivity: "base", numeric: true });
const pages = dv.pages('"09_ナレッジベース"')
  .where(p => Array.from(p.tags ?? []).some(tag => String(tag).startsWith("言語/")))
  .array()
  .sort((a, b) => collator.compare(String(a.sort_yomi ?? a.file.name), String(b.sort_yomi ?? b.file.name)));
dv.list(pages.map(p => p.file.link));
```

## 科学

```dataviewjs
const collator = new Intl.Collator("ja", { sensitivity: "base", numeric: true });
const pages = dv.pages('"09_ナレッジベース"')
  .where(p => Array.from(p.tags ?? []).some(tag => String(tag).startsWith("科学/")))
  .array()
  .sort((a, b) => collator.compare(String(a.sort_yomi ?? a.file.name), String(b.sort_yomi ?? b.file.name)));
dv.list(pages.map(p => p.file.link));
```

## 技術

```dataviewjs
const collator = new Intl.Collator("ja", { sensitivity: "base", numeric: true });
const pages = dv.pages('"09_ナレッジベース"')
  .where(p => Array.from(p.tags ?? []).some(tag => String(tag).startsWith("技術/")))
  .array()
  .sort((a, b) => collator.compare(String(a.sort_yomi ?? a.file.name), String(b.sort_yomi ?? b.file.name)));
dv.list(pages.map(p => p.file.link));
```

## 社会

```dataviewjs
const collator = new Intl.Collator("ja", { sensitivity: "base", numeric: true });
const pages = dv.pages('"09_ナレッジベース"')
  .where(p => Array.from(p.tags ?? []).some(tag => String(tag).startsWith("社会/")))
  .array()
  .sort((a, b) => collator.compare(String(a.sort_yomi ?? a.file.name), String(b.sort_yomi ?? b.file.name)));
dv.list(pages.map(p => p.file.link));
```

## 文化

```dataviewjs
const collator = new Intl.Collator("ja", { sensitivity: "base", numeric: true });
const pages = dv.pages('"09_ナレッジベース"')
  .where(p => Array.from(p.tags ?? []).some(tag => String(tag).startsWith("文化/")))
  .array()
  .sort((a, b) => collator.compare(String(a.sort_yomi ?? a.file.name), String(b.sort_yomi ?? b.file.name)));
dv.list(pages.map(p => p.file.link));
```
