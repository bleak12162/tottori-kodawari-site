# 株式会社鳥取こだわり野菜の会（静的サイト）

このフォルダは **Vercel にそのままデプロイできる静的サイト**です。

Vercel の公式KBでは、**"Other frameworks"（静的HTMLを含む）では `public/` 配下が優先**されると案内されています。  
そのため、このパッケージは `public/index.html` にしています。  
（公式KB：`public` を優先）  

## デプロイ方法（Git連携）
1. このフォルダを GitHub リポジトリにアップ（`public/` を含める）
2. Vercel ダッシュボード → New Project → Git リポジトリを Import → Deploy

Vercel は Git を接続すると、コミットごとに自動デプロイされます。  

## デプロイ方法（CLI）
ターミナルでこのフォルダへ移動して:

```bash
npx vercel
```

初回は質問に答えるだけで Preview デプロイされます。  
本番反映は:

```bash
npx vercel --prod
```

## 写真の差し替え
現状は「グラデーションの仮背景」です。`public/index.html` のCSS先頭の変数を置き換えるだけでOKです。

例：`public/hero.jpg` を置いて

```css
--hero-photo: url("/hero.jpg") center/cover no-repeat;
```

同様に：
- `--story-photo`（生産者・手元）
- `--quality-photo`（出荷・品質管理）

## 取り扱い品目表の編集
`public/index.html` の `#items` セクションの `<tbody>` を実データに差し替えてください。
（認証区分：有機JAS / 特別栽培 / 慣行）

## 注意
`sitemap.xml` のURL（example...）は、公開URLに合わせて変更してください。
