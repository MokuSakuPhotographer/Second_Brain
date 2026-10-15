```dataview
TABLE file.tags AS "カテゴリ", file.ctime AS "作成日時"
FROM "09_ナレッジベース/wikipedia"
SORT file.ctime DESC
```