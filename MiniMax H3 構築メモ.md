ノイズシード：757358688076805

---

# Setupテンプレート

> [!NOTE]
> initial_prompt:
> [場所や構図の概要]。[主役]に[出来事]が起きる。[見せたい全体の雰囲気]。
> 
> duration_seconds:
> [秒数]
> 
> visual_style:
> [例: cinematic, live-action, realistic, soft indoor lighting]
> 
> overall_soundscape:
> [環境音]。[必要な効果音]を[どういう質感で]、[映像とどう同期させるか]。
> 
> non_diegetic_music:
> [N/A または BGMの有無]

# Image Referenceのテンプレート

> [!NOTE]
> image_use:
> Exact first frame
> 
> reference_name:
> [主役の対象名]
> 
> description:
> [画像全体の説明]。[主役]を中心に扱う。[何を忠実に維持したいか]。
> 
> content_type:
> [object / scene / person など適切なもの]
> 
> subject_name:
> [主役の具体名]
> 
> retention:
> Auto for this relationship
> 
> shot_scope:
> [どのショットでどう使うか]
> 
> transfer_target_subject:
> [必要な場合のみ]

# Shot の書き方

## Shot description の書き方ルール

### ルール1：時系列で書く

時刻順に並べる。

### ルール2：1行1イベント群

1つの時刻に起きることをまとめて書く。

### ルール3：同時なら同じ時刻に書く

別の時刻へ分けない。

### ルール4：被写体とカメラを区別する

できればカメラは `camera_direction` に分離。

### ルール5：音を省略しない

音が重要なら必ず書く。

> [!descriptionの例]
> 0:00 左側の黒い携帯電話に着信があり、画面が点灯する。着信音が鳴り始め、同時に携帯電話が振動する。
> 0:02 左側の黒い携帯電話のディスプレイが見やすいように、その携帯電話を中心に見せる。
> 0:04 カメラがゆっくり引き、元の全景に戻る。着信音と振動は自然に弱まりながらショットが終わる。

## camera_direction のおすすめ書き方

descriptionにカメラまで全部混ぜても動くが、  分けられるなら分けた方が綺麗。

> [!directionの例]
> 0:00 静止したワイドショットで開始する。
> 0:02 カメラが左側の黒い携帯電話へゆっくり寄る。
> 0:04 カメラがゆっくり引き、全体の構図に戻る。