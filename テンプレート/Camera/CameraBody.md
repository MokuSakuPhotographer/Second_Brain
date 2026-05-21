---
type: camera_body
名前: <% tp.file.title %>
カテゴリ: カメラ本体
メーカー: <% await tp.system.prompt("メーカー") %>
マウント: <% await tp.system.prompt("マウント") %>
センサー: <% await tp.system.prompt("センサー") %>
有効画素数:
購入日: <% tp.date.now("YYYY-MM-DD") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

用途:
  - <% await tp.system.prompt("主な用途") %>

関連機材:
  - "[[]]"

tags:
  - カメラ
  - 撮影
---

