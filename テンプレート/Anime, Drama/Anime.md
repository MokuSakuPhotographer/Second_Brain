---
type: anime
名前: <% tp.file.title %>
レート: <% await tp.system.prompt("レート 例: 5") %>
視聴状況: <% await tp.system.prompt("視聴状況 例: 全部観た / 途中") %>
作成日: <% tp.date.now("YYYY-MM-DD") %>

好きなキャラ:
  - <% await tp.system.prompt("好きなキャラ") %>

備考:

関連作品:
  - "[[]]"

関連キャラ:
  - "[[]]"

tags:
  - anime
  - <% await tp.system.prompt("追加タグ 例: 泣いた / SF / 異世界") %>
---
