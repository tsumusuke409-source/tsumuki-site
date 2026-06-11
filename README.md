# 積木進之介 — 個人サイト

## ローカル起動

```bash
cd Desktop/tsumuki-site
npm install
npm run dev
```

ブラウザで http://localhost:5185 を開く。

---

## 写真の配置

以下のパスに画像ファイルを置いてください。

| ファイル | 内容 |
|---|---|
| `public/images/hero.jpg` | ヒーロー写真（札幌の屋外写真） |
| `public/images/bodybuilding.jpg` | ボディビル大会の写真 |

### 写真のトリミングについて

- **hero.jpg（ヒーロー）**: CSS で右側のみを表示するよう自動クロップしています。右側の人物が中央に来るよう調整済みです。ずれる場合は `src/styles/global.css` の `.hero-photo-frame img` の `width` 値（デフォルト `200%`）を調整してください。
- **bodybuilding.jpg（About）**: 左側から表示し、右端が自動クロップされます。`.about-photo-frame img` の `width` 値（デフォルト `120%`）で調整できます。

---

## 活動報告の追加方法

`src/content/activities/` フォルダに Markdown ファイルを1つ追加するだけです。

### ファイル名のルール

```
YYYY-MM-記事スラッグ.md
```

例: `2025-03-ai-workshop.md`

### テンプレート

```markdown
---
title: 記事タイトル
date: 2025-03-15
description: 一覧や SNS シェア時に表示される短い説明文（60〜120字程度）
tags: ["タグ1", "タグ2"]          # 省略可
image: /images/記事画像.jpg       # 省略可（public/images/ に置く）
---

## 見出し

本文をここに書く。普通のMarkdownが使えます。

**太字**、*イタリック*、[リンク](https://example.com) など。
```

ファイルを保存すると、`/activities/` 一覧とトップページに自動で表示されます。

---

## X (Twitter) リンクの差し替え

`src/pages/index.astro` の最下部にある Contact セクションの URL を変更してください。

```astro
<a href="https://twitter.com/YOUR_HANDLE" ...>
```

`YOUR_HANDLE` の部分を自分の X ハンドルに置き換えてください。

---

## ビルド & デプロイ（Vercel）

```bash
npm run build   # dist/ フォルダが生成される
```

Vercel に GitHub リポジトリを連携するだけで自動デプロイされます。
Framework Preset は **Astro** を選択してください。
