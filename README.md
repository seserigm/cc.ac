---
theme: jekyll-theme-cayman
lang: ja-JP
title: アカクロ用シナリオ整形ツール
---


## 概説

Archive Chronicle掲載用の書式に整えるツール。

## 処理内容

### 初期処理

- 文中の半角の英数、記号、空白を全角に変換
- 行頭の "「" の前後にある1つ以上の空白を削除
- "」" の前にある1つ以上の空白を削除
- 行末にある1つ以上の空白を削除

### 会話フラグ

- 行頭に "「" があったら OPEN
- 行末に "」" があったら CLOSE
- 行頭に 空白 があったら SPACE

### フロー

もし TALK:OFF かつ OPEN:ON かつ CLOSE:OFF なら

- TALK:ON

そうでなく TALK:ON のとき

- もし SPACE:OFF なら 行頭に空白を追加
- もし CLOSE:ON かつ OPEN:OFF なら TALK:OFF

## 予定

- 鉤括弧内の括弧に応じてインデント数を変更

```text
「（こういうとき
　　２つ空白を入れたい）」
```
