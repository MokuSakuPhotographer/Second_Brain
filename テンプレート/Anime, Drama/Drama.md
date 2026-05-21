---
type: drama
名前: <% tp.file.title %>
シリーズ: <% await tp.system.prompt("シリーズ名 例: ブラック・ミラー") %>
レート: <% await tp.system.prompt("レート 例: 5") %>
視聴状況: <% await tp.system.prompt("視聴状況 例: 全部観た") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

あらすじ:

風刺:

関連作品:
  - "[[]]"

テーマ:
  - "[[]]"

tags:
  - drama
  - <% await tp.system.prompt("追加タグ 例: SNS / AI / 資本主義") %>
---

