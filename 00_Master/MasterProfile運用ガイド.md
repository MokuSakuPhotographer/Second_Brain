## 概要

[[MasterProfile]]は「自分自身をAIに説明するためのプロフィール」です。

人間向けの自己紹介ではなく、ChatGPTやClaudeなどのAIが私の状況、価値観、環境、目標を理解するための知識ベースとして利用します。

---

# ファイル構成

```text
00_Master
│
├─ README.md
├─ MasterProfile.md
├─ CurrentFocus.md
├─ MonthlyReview.md
└─ AI_Instructions.md
```

---

# 各ファイルの役割

## [[MasterProfile]].md

変化しにくい情報を管理する。

例

- 基本情報
- 仕事
- 趣味
- カメラ機材
- PC環境
- 英語学習
- 価値観
- 判断基準


更新頻度：

年数回～月1回程度

---

## CurrentFocus.md

現在取り組んでいることを管理する。

例

- 現在のプロジェクト
- 現在の学習内容
- 現在の課題
- 今月達成したいこと


更新頻度：

週1回～月1回

---

## MonthlyReview.md

Dataviewで生成される更新ノート一覧。

役割：

最近変更したノートを確認するためのダッシュボード。

AIに渡すためのファイルではない。

更新頻度：

自動

---

## AI_Instructions.md

AIへの回答方針を記録する。

例

- 回答スタイル
- 優先事項
- 回避してほしいこと


更新頻度：

必要時のみ

---

# 基本運用

## 日常

通常通りObsidianを使用する。

[[MasterProfile]]を頻繁に編集する必要はない。

---

## 月次レビュー

MonthlyReviewを確認する。

更新されたノート一覧から、

以下に該当するノートを探す。

### [[MasterProfile]]更新候補

- 新しい趣味
- 新しい目標
- 新しい機材
- 新しいプロジェクト
- 価値観の変化
- 学習方針の変化


### CurrentFocus更新候補

- 今取り組んでいること
- 今月の課題
- 今月の目標


---

# AIによる更新プロセス

## Step1

以下をAIへ渡す。

```text
MasterProfile.md
CurrentFocus.md
```

## Step2

MonthlyReviewを確認し、

プロフィール更新に関係しそうなノートを選ぶ。

例

```text
ホームシアター構築.md
AD100ProⅡ.md
英語学習.md
```

## Step3

選択したノートもAIへ渡す。

## Step4

AIへ依頼する。

```text
これらの内容を反映して
MasterProfile.mdとCurrentFocus.mdを更新してください。
```

## Step5

提案内容を確認し、
問題なければ反映する。

---

# AI Summaryについて

MasterProfile上部の

```markdown
## AI Summary
```

は手動で編集しない。

プロフィール全体が更新された後に、

AIへ以下を依頼する。

```text
MasterProfileを読んで
AI Summaryを再生成してください。
```

更新頻度：

3〜6か月に1回

---

# 更新判断基準

以下は更新しない。

- 日記
- 一時的な感想
- 一時的なゲーム記録
- 一時的な買い物メモ


以下は更新対象。

- 長期的な目標
- 習慣
- 趣味
- 所有機材
- 仕事環境
- 学習状況
- 判断基準
- 価値観


---

# このシステムの目的

目的はプロフィール管理ではない。

AIが私を理解するための知識ベースを維持することである。

MasterProfileは「私とは何者か」。

CurrentFocusは「私は今何をしているか」。

この2つを維持することで、AIからより正確で個人最適化された提案を受けられる状態を保つ。