---
type: lighting
名前: <% tp.file.title %>
カテゴリ: ライティング
メーカー: <% await tp.system.prompt("メーカー") %>
種類: <% await tp.system.prompt("種類 例: ストロボ / ソフトボックス / トリガー") %>
対応:
購入日: <% tp.date.now("YYYY-MM-DD") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

関連機材:
  - "[[SONY α7Ⅴ]]"

tags:
  - ライティング
  - 撮影
  - <% await tp.system.prompt("追加タグ 例: Godox") %>
---

