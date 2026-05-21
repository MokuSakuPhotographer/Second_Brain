---
type: lens
名前: <% tp.file.title %>
カテゴリ: レンズ
メーカー: <% await tp.system.prompt("メーカー") %>
マウント: Sony E
焦点距離: <% await tp.system.prompt("焦点距離 例: 85mm / 70-180mm") %>
開放F値: <% await tp.system.prompt("開放F値 例: F1.4 / F2.8") %>
種類: <% await tp.system.prompt("種類 例: 単焦点 / 標準ズーム / 望遠ズーム") %>
フィルター径:
購入日: <% tp.date.now("YYYY-MM-DD") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

用途:
  - <% await tp.system.prompt("主な用途 例: ポートレート") %>

関連機材:
  - "[[SONY α7Ⅴ]]"
  - "[[SONY α7Ⅳ]]"

tags:
  - レンズ
  - 撮影
  - <% await tp.system.prompt("追加タグ 例: ポートレート") %>
---

