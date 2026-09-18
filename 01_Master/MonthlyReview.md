# 最近更新したノート

```dataview
TABLE file.mtime
FROM ""
WHERE file.mtime >= date(today) - dur(30 days)
SORT file.mtime DESC
```