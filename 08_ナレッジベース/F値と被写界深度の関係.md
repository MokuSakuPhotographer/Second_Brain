---
tags:
- 技術/カメラ
- 文化/写真
source: []
created: 2026-09-21
updated: 2026-09-21
aliases: []
status: researched
schema: nova-obsidian-research-v1
note_status: draft
related_notes:
- 08_ナレッジベース/テーブルフォト参考レポート.md
- 08_ナレッジベース/次に購入すべきレンズ.md
---

# F値と被写界深度の関係

<!-- BODY_START -->

## F値とは何か

<!-- P001 -->
F値（f-number）は、レンズの焦点距離を有効口径（より厳密には入射瞳の直径）で割った比です。したがって同じ焦点距離なら、F値が小さいほど開口は大きくなり、より太い光束がレンズを通ります。たとえば50 mmレンズをF2で使う場合、単純化した入射瞳径は約25 mmです。[^1][^2]

## 小さいF値で被写界深度が浅くなる理由

<!-- P002 -->
被写界深度は、ピント面の前後で「許容できるほど鮮明」に見える距離範囲です。ピント面上の点からの光は撮像面上の点へ収束しますが、前後に外れた物体の光は円状に広がります。この広がりが許容錯乱円を超えると、鮮明とはみなされません。[^2][^3]

<!-- P003 -->
小さいF値では開口が大きく、光線束の円錐角が大きくなります。そのため撮像面が正しい結像位置から同じ量だけ外れた場合でも錯乱円が大きくなり、許容範囲を早く超えます。ほかの条件が同じなら、F値を小さくするほど被写界深度は浅くなりやすく、F値を大きくするほど深くなります。[^2][^4][^5]

## 焦点距離と撮影距離

<!-- P004 -->
カメラ位置、被写体までの距離、F値を固定した比較では、焦点距離が長いほど像倍率が高くなり、一般に被写界深度は浅くなります。ただし画角が変わるため、写真の構図は同じではありません。[^5][^6][^3]

<!-- P005 -->
被写体を画面内で同じ大きさに保つため、長い焦点距離では後退し、短い焦点距離では接近する比較では、通常の撮影距離における総被写界深度は焦点距離だけでは大きく変わらない場合があります。一方、長焦点側では背景が大きく写り、ボケも拡大されるため、背景がよりぼけて見えることがあります。これは「許容鮮明範囲としての被写界深度」と「ピント外領域のボケの見え方」が同一ではないためです。[^3][^2]

<!-- P006 -->
焦点距離とF値を固定したまま被写体へ近づくほど像倍率が上がり、被写界深度は浅くなります。逆に被写体から離れるほど被写界深度は深くなります。背景を大きくぼかしたい場合は、被写体へ近づくだけでなく、被写体と背景の距離を広げることも有効ですが、後者は背景側のボケ量を変える操作であり、被写界深度そのものの定義とは分けて扱う必要があります。[^5][^3]

## センサーサイズを比較するときの条件

<!-- P007 -->
センサーサイズだけで被写界深度が決まるわけではありません。同じ撮影位置、同じ画角、同じ構図、同じF値で比較するには、センサーが大きい側ほど長い焦点距離が必要です。この条件では入射瞳も大きくなるため、大きいセンサー側の被写界深度は浅くなりやすくなります。反対に、同じ焦点距離・同じ撮影距離・同じF値なら画角と構図が変わるため、単純なセンサーサイズ比較にはなりません。最終的な見え方は許容錯乱円、表示サイズ、観察距離にも依存します。[^7][^8][^3]

## 実用上の整理

<!-- P008 -->
被写界深度を浅くしやすい基本操作は、F値を小さくする、被写体へ近づく、同じ撮影位置なら焦点距離を長くする、の三つです。ただし構図を一定にする比較では焦点距離と撮影距離が連動します。背景分離を評価するときは、被写界深度だけでなく、被写体から背景までの距離、背景の拡大率、ボケの形や描写も別に確認します。[^4][^5][^3]

<!-- BODY_END -->

<!-- SOURCES_START -->

## 出典

[^1]: Nikon「COOLPIX P6000 User's Manual — Aperture and Zoom」 https://www.nikonusa.com/pdf/manuals/noprint/P6000_ennoprint.pdf
[^2]: ZEISS「Depth of Field and Bokeh」 https://lenspire.zeiss.com/photo/app/uploads/2022/02/technical-article-depth-of-field-and-bokeh.pdf
[^3]: Cambridge in Colour「Understanding Depth of Field in Photography」 https://www.cambridgeincolour.com/tutorials/depth-of-field.htm
[^4]: Nikon「Understanding Maximum Aperture」 https://www.nikonusa.com/learn-and-explore/c/tips-and-techniques/understanding-maximum-aperture
[^5]: Canon「Depth of field — RF LENS WORLD」 https://files.canon-europe.com/files/webcontent/rf-lens-world/knowledge/depth-of-field/index.html
[^6]: Nikon「Understanding Focal Length」 https://www.nikonusa.com/learn-and-explore/c/tips-and-techniques/understanding-focal-length
[^7]: ZEISS「Depth of Field and Manual Focusing」 https://lenspire.zeiss.com/photo/en/article/depth-of-field-and-manual-focusing
[^8]: Cambridge in Colour「Digital Camera Sensor Sizes: How it Influences Your Photography」 https://cdn.cambridgeincolour.com/tutorials/digital-camera-sensor-size.htm

<!-- SOURCES_END -->
