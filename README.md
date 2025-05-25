# TODO アプリ

このプロジェクトはCloudflare WorkersとHonoフレームワークを使用したTODOアプリです。
ポートフォリオ用に作成されたシンプルなタスク管理アプリケーションです。

## 機能

- タスクの追加、閲覧、編集、削除機能
- Cloudflare KVを使用したデータの永続化
- レスポンシブデザインのUIインターフェース

## 技術スタック

- [Hono](https://honojs.dev/) - 軽量で高速なWebフレームワーク
- [Cloudflare Workers](https://workers.cloudflare.com/) - エッジコンピューティングプラットフォーム
- TypeScript - 型安全なJavaScript
- HTML/CSS - フロントエンドインターフェース

## 開発を始める

### 前提条件

- Node.js (v16以上)
- npm または yarn
- Cloudflareアカウント（デプロイする場合）

### インストール

```txt
npm install
npm run dev
```

開発サーバーが起動し、`http://localhost:8787` でアプリにアクセスできます。

### デプロイ

Cloudflare Workersにデプロイするには以下のコマンドを実行します：

```txt
npm run deploy
```

### 型の生成

[For generating/synchronizing types based on your Worker configuration run](https://developers.cloudflare.com/workers/wrangler/commands/#types):

```txt
npm run cf-typegen
```

Pass the `CloudflareBindings` as generics when instantiation `Hono`:

```ts
// src/index.ts
const app = new Hono<{ Bindings: CloudflareBindings }>()
```

## プロジェクトの構造

```
src/
├── index.ts       # アプリケーションのエントリーポイント
├── todos/         # TODOに関連するハンドラとモデル
├── middleware/    # ミドルウェア
└── utils/         # ユーティリティ関数
```

## 作者

あなたの名前をここに記入してください

## ライセンス

MIT
