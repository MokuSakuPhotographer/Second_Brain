---
aliases:
  - TP-Link Tapo C200
  - Tapo C200
tags:
  - 機械ペット
  - Tapo
  - ネットワークカメラ
  - 製品仕様
manufacturer: TP-Link
product_name: Tapo C200
product_type: パンチルト ネットワークWi-Fiカメラ
use_case:
  - 屋内見守り
  - ペットカメラ
  - 防犯カメラ
  - 自律対話型機械ペットの視覚入力
project_role:
  - 視界取得
  - 首振り表現
  - 人物検知トリガー
  - 見守り用カメラ
camera_resolution: 1080p / 1920x1080px
frame_rate: 15fps
image_sensor: 1/3インチ プログレッシブスキャンCMOS
lens: 4mm / F2.0
field_of_view: 対角88.3度 / 水平75.2度 / 垂直40.8度
video_compression: H.264
image_enhancement: 3DNR
pan_tilt_range: 水平360度 / 垂直114度
night_vision: 850nm IR LED / 最長12m
audio_input_output: 内蔵マイク / 内蔵スピーカー
two_way_audio: 対応 / ノイズキャンセリング搭載
detection:
  - 動体検知
  - 人物検知
  - 赤ちゃんの泣き声検知
activity_zones: 対応
notification:
  - システム通知
  - スナップショット付き通知（Tapo Care利用時）
  - クリップ付き通知（Tapo Care利用時）
local_storage: microSDカード 最大512GB
cloud_storage: Tapo Care 有償サービス
network_connection: Wi-Fi
wifi_protocol: IEEE 802.11b/g/n / 2.4GHz
rtsp: 対応
onvif: 対応
power_source: 9V DC電源アダプター
power_consumption: 標準2.0W / 最大4.5W
mounting: 据え置き / 天井取り付け
operating_temperature: 0度から40度
weight: 190g
hardware_version: 要確認
source:
  - https://www.tp-link.com/jp/home-networking/cloud-camera/tapo-c200/
  - https://www.tp-link.com/us/home-networking/cloud-camera/tapo-c200/
---

# Tapo C200 製品仕様詳細

## 位置づけ

Tapo C200は、このプロジェクトでは「自律対話型機械ペット」の目と首にあたる部品として扱う。
単体の防犯カメラとしてではなく、RTSP映像、人物検知、パン・チルト、外部AI発話システムを組み合わせるための入力装置として整理する。

関連ノート: [[自律対話型機械ペット構築計画]]

## 構築上重要なプロパティ

| プロパティ | 意味 |
|---|---|
| `rtsp` | PythonやHome Assistantで映像ストリームを取得するために重要 |
| `onvif` | 外部システムからカメラ制御するために重要 |
| `pan_tilt_range` | キョロキョロする、見回す、注視する動きの基礎 |
| `detection` | マスターの入室・在席・離席判定のトリガー候補 |
| `two_way_audio` | 標準機能としては通話中心。自発発話はVOICEVOXなど外部音声が現実的 |
| `night_vision` | 暗い部屋での見守りや人物認識に関係する |
| `local_storage` | カメラ単体で録画を残す場合に関係する |

## 機械ペット用途での読み替え

| カメラ機能 | 機械ペットとしての役割 |
|---|---|
| パン・チルト | 首振り、見回し、興味を示す動作 |
| RTSP | Python側で現在の視界を取得する |
| ONVIF | 首の向きやプリセット移動を外部制御する |
| 人物検知 | マスター発見、帰宅、離席の判断材料 |
| 内蔵マイク・スピーカー | 通話用。任意の自律発話は外部スピーカー利用を優先 |
| ナイトビジョン | 夜間・暗所でも見守りを継続する |

## 現時点の判断

- 映像取得はRTSPを使う。
- 人物認識はTapo本体の検知だけでなく、Python側のYOLOv8でも扱う。
- 発話はTapo C200内蔵スピーカーへ直接流すより、VOICEVOXとPCスピーカーを使う構成が現実的。
- 首振り制御はONVIFまたはHome Assistant経由での安定性確認が必要。

## 要確認

- 使用中のTapo C200本体のハードウェアバージョン。
- ONVIF経由でパン・チルト制御がどこまで安定するか。
- 内蔵スピーカーへ任意音声を直接流せるか。
- 長時間稼働時の発熱、ネットワーク切断、RTSP再接続の安定性。
