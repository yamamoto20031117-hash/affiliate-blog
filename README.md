# Affiliate Blog — Astro + Tailwind CSS テンプレート

スマホ対応・SEO配慮済みのアフィリエイトブログひな型です。

## セットアップ

```bash
npm install
npm run dev      # 開発サーバー起動 → http://localhost:4321
npm run build    # 本番ビルド
npm run preview  # ビルド結果をプレビュー
```

## ディレクトリ構成

```
src/
├── components/
│   ├── Header.astro          # ヘッダー（レスポンシブ対応）
│   ├── Footer.astro          # フッター
│   ├── ArticleCard.astro     # 記事カードコンポーネント
│   ├── AffiliateBox.astro    # 商品紹介ボックス
│   └── TableOfContents.astro # 自動生成目次
├── content/
│   ├── config.ts             # コレクション定義（型定義）
│   └── posts/                # Markdown記事ファイル
├── layouts/
│   ├── BaseLayout.astro      # 共通レイアウト（SEOタグ込み）
│   └── PostLayout.astro      # 記事ページレイアウト
├── pages/
│   ├── index.astro           # トップページ
│   ├── about.astro           # ブログ紹介ページ
│   ├── contact.astro         # お問い合わせ
│   ├── disclaimer.astro      # 免責事項
│   ├── privacy.astro         # プライバシーポリシー
│   └── posts/
│       ├── index.astro       # 記事一覧
│       └── [slug].astro      # 記事詳細（動的ルート）
└── styles/
    └── global.css            # グローバルスタイル
```

## 記事の書き方

`src/content/posts/` に `.md` または `.mdx` ファイルを作成します。

```markdown
---
title: "記事タイトル"
description: "記事の説明文（SEOに使用）"
pubDate: 2024-12-01
updatedDate: 2024-12-10   # 任意
category: "ガジェット"
tags: ["タグ1", "タグ2"]
featured: true              # トップページの注目記事に表示
heroImage: "/images/hero.jpg"  # アイキャッチ画像（任意）
affiliates:
  - name: "商品名"
    description: "商品説明"
    price: "¥1,980"
    url: "https://affiliate-link.com"
    badge: "人気No.1"       # 任意
    rating: 4.5             # 任意（0〜5）
    image: "/images/product.jpg"  # 任意
---

## 記事本文

ここに記事を書きます。
```

## カスタマイズ

### ブログ名・サイトURLの変更

- `astro.config.mjs` の `site` を本番URLに変更
- `src/components/Header.astro` のロゴテキストを変更
- `src/components/Footer.astro` のブログ名・説明を変更
- `src/layouts/BaseLayout.astro` の `<title>` サフィックスを変更

### カテゴリの追加

`src/components/Header.astro` の `navLinks` 配列に追加してください。

### アフィリエイト免責文の編集

`src/components/Footer.astro` の免責文テキストを編集してください。

### お問い合わせフォームの有効化

1. [Formspree](https://formspree.io) でフォームを作成
2. `src/pages/contact.astro` の `action` URLのフォームIDを置き換え

### Google Analytics の追加

`src/layouts/BaseLayout.astro` の `<head>` 内に GA4 スニペットを追加してください。

## 技術スタック

- [Astro](https://astro.build/) v4
- [Tailwind CSS](https://tailwindcss.com/) v3
- [@astrojs/tailwind](https://docs.astro.build/en/guides/integrations-guide/tailwind/)
- [@astrojs/mdx](https://docs.astro.build/en/guides/integrations-guide/mdx/)
