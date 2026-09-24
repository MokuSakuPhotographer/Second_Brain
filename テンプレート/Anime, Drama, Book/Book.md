---
type: book
名前: <% tp.file.title %>
レート: <% await tp.system.prompt("レート 例: 5") %>
視聴状況: <% await tp.system.prompt("進捗 例: 読了 / 途中") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>
関連:
  - "[[]]"
tags:
  - 
媒体: <% await tp.system.prompt("媒体 例: 紙 / 電子") %>
---

## 備考
