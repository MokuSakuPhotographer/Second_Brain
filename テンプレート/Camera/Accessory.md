---
type: accessory
名前: <% tp.file.title %>
カテゴリ: 周辺機器
メーカー: <% await tp.system.prompt("メーカー") %>
種類: <% await tp.system.prompt("種類 例: ストラップ / クランプ / ケース") %>
購入日: <% tp.date.now("YYYY-MM-DD") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

関連機材:
  - "[[]]"

tags:
  - 周辺機器
  - 撮影
---

