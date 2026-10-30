# 自己管理・日次 MOC

[[Home|← Home]]

## マスター情報

- [[MasterProfile]]
- [[CurrentFocus]]
- [[LongTermGoals]]
- [[MonthlyReview]]

## 月別アーカイブ

```dataview
LIST
FROM "05_Daily/Monthly"
WHERE type = "monthly"
SORT file.name DESC
```

## 直近30日の日次ノート

本日を含む直近30日間の記録を表示します。

```dataview
LIST
FROM "05_Daily"
WHERE type = "daily" AND date >= date(today) - dur(29 days) AND date <= date(today)
SORT date DESC
```
