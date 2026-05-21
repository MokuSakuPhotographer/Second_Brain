---
type: filter
名前: <% tp.file.title %>
カテゴリ: フィルター
メーカー: <% await tp.system.prompt("メーカー") %>
種類: <% await tp.system.prompt("種類 例: CPL / ND / ブラックミスト") %>
径: <% await tp.system.prompt("径 例: 77mm") %>
方式:
購入日: <% tp.date.now("YYYY-MM-DD") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

関連機材:
  - "[[]]"

tags:
  - フィルター
  - 撮影
---

