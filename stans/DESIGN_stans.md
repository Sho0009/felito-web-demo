# DESIGN.md — stans.jp

> 参考サイト: https://stans.jp/
> 分析日: 2026-04-07
> 業種: クリエイティブエージェンシー コーポレートサイト

---

## 1. Visual Theme & Atmosphere

- **デザイン方針**: ビジネス課題の解決とビジュアルの美しさを両立させたダーク×カラフルアクセントのクリエイティブエージェンシースタイル
- **密度**: 中〜高。プロジェクトポートフォリオを前面に出しつつ、サービス説明も充実させた業務型レイアウト
- **キーワード**: クリエイティブ、ダーク、ポートフォリオ、モダン、専門性

---

## 2. Color Palette & Roles

> ダークトーンをベースに複数のアクセントカラーを組み合わせる。クリエイティブエージェンシーらしい視覚的インパクトを演出。

### Primary（ブランドカラー）

- **Primary** (`#1e1e1e`): メインの黒に近い濃いグレー（`base-black`）
- **Primary Dark** (`#111111`): さらに深いブラック

### Accent Colors（複数使用）

- **Blue** (`#0057ff` 推定): `base-blue` — プライマリアクセント
- **Orange** (`#ff6b35` 推定): `base-orange` — 強調・CTA
- **Green** (`#00b894` 推定): `base-green` — サクセス・カテゴリ
- **Yellow** (`#fdcb6e` 推定): `base-yellow` — ハイライト・タグ

### Semantic（意味的な色）

- **Danger** (`#e17055`): エラー・削除（オレンジ系に近い危険色）
- **Warning** (`#fdcb6e`): 警告（`base-yellow` を流用）
- **Success** (`#00b894`): 成功（`base-green` を流用）

### Neutral（ニュートラル）

- **Text Primary** (`#ffffff`): ダーク背景上の白テキスト
- **Text Secondary** (`#aaaaaa`): 補足テキスト・ラベル（薄いグレー）
- **Text Disabled** (`#555555`): 非活性状態
- **Border** (`#333333`): 区切り線（ダーク背景に合わせた控えめなボーダー）
- **Background** (`#1e1e1e`): ページ基本背景（`base-black`）
- **Dark Gray** (`#2c2c2c`): カード・セクション背景（`base-dark-gray`）

---

## 3. Typography Rules

### 3.1 和文フォント

- **ゴシック体**: スタンダードなゴシック体（Noto Sans JP または游ゴシック）
- ブランド名「スタンス」は日本語・英語を併記するため、和欧組み合わせに特に注意

### 3.2 欧文フォント

- **サンセリフ**: グロテスク系（Helvetica Neue / Neue Haas Grotesk 等）
- **等幅**: コード表示等に利用する場合は Consolas / Menlo

### 3.3 font-family 指定（推定）

```css
/* 本文 */
font-family: "Noto Sans JP", "游ゴシック", "Yu Gothic", Helvetica, sans-serif;

/* 英語見出し */
font-family: "Helvetica Neue", Arial, sans-serif;

/* 等幅 */
font-family: "SFMono-Regular", Consolas, Menlo, monospace;
```

### 3.4 文字サイズ・ウェイト階層

| Role | Font | Size | Weight | Line Height | Letter Spacing | 備考 |
|------|------|------|--------|-------------|----------------|------|
| Display | ゴシック/欧文 | 42px+ (`huge`) | 700 | 1.1 | -0.01em | ヒーロー大見出し |
| Heading 1 | ゴシック | 32–40px | 600–700 | 1.2 | 0em | セクション見出し |
| Heading 2 | ゴシック | 22–28px | 600 | 1.35 | 0.01em | サブ見出し |
| Heading 3 | ゴシック | 18–20px | 500 | 1.5 | 0.01em | 小見出し |
| Body | ゴシック | 16px | 400 | 1.75 | 0.03em | 本文（`base` 16px） |
| Caption | ゴシック | 12–13px | 400 | 1.6 | 0.05em | 補足・タグ |

### 3.5 行間・字間

- **本文の行間 (line-height)**: 1.7〜1.8
- **見出しの行間**: 1.1〜1.3
- **本文の字間 (letter-spacing)**: 0.03em
- **見出しの字間**: 0〜0.01em（タイトは大きく見せる）

### 3.6 禁則処理・改行ルール

```css
word-break: break-all;
overflow-wrap: break-word;
line-break: strict;
```

### 3.7 OpenType 機能

```css
font-feature-settings: "palt" 1, "kern" 1;
```

### 3.8 縦書き

該当なし

---

## 4. Component Stylings

### Buttons

**Primary**
- Background: アクセントカラー（`#0057ff` または `#ff6b35`）
- Text: `#ffffff`
- Padding: 14px 36px
- Border Radius: 0px or 4px（エッジは角ばっている）
- 右矢印アイコン付き（SVG白矢印）

**Secondary（アウトライン）**
- Background: `transparent`
- Text: `#ffffff`
- Border: 1px solid `#ffffff` or `#aaaaaa`
- Padding: 12px 28px

**テキストリンク**
- Text: `#ffffff` + 右向き白矢印アイコン
- 例: "Contact →", "Service Detail →", "Projects →"

### Cards（プロジェクト一覧）

- Background: `#2c2c2c`（`base-dark-gray`）
- Border: なし
- Border Radius: 0–4px
- Padding: 0px（画像フル表示） + テキストエリア 16–24px
- Hover: 画像オーバーレイ or 輝度変化

### Navigation

- 項目: "our shop" / "project" / "menu"（シンプルな3項目）
- ロゴ: 左上
- カラー: ダーク背景に白テキスト
- スタイル: フラットテキスト or ハンバーガーメニュー

---

## 5. Layout Principles

### Spacing Scale

| Token | Value |
|-------|-------|
| XS | 8px |
| S | 16px |
| M | 32px |
| L | 56px |
| XL | 80px |
| XXL | 120px |

### Container

- Max Width: 1280px
- Padding (horizontal): 40–64px

### Grid

- Columns: 12カラム
- Gutter: 24px
- プロジェクト一覧: 2〜3カラムのグリッド
- ヒーロー: フルスクリーンスライダー（8枚）

### セクション構成

1. **Hero** — 8枚画像スライダー + キャッチコピー
2. **Projects** — プロジェクトポートフォリオグリッド
3. **Services** — サービス説明（テキスト＋ビジュアル）
4. **Workflow** — ワークフロー説明（ステップ型）
5. **Company Info** — 会社情報テキストセクション
6. **Contact** — コンタクトCTA
7. **Footer** — ナビゲーション・コピーライト

---

## 6. Depth & Elevation

| Level | Shadow | 用途 |
|-------|--------|------|
| 0 | none | 基本フラット |
| 1 | `0 4px 16px rgba(0,0,0,0.3)` | カードホバー（ダーク背景なので影は深め） |

---

## 7. Animation & Interaction

- **ヒーロースライダー**: 8枚画像の自動スライド
- **ローディングアニメーション**: 10枚のローディング画像シーケンス
- **リンクプリフェッチ**: conservative 設定での先読み最適化
- **ホバー効果**: 矢印アイコンの位置変化 or カード輝度変化
- **スクロール連動**: 要素のフェードイン

### パターン背景

- 160×40px のテクスチャパターンをセクション背景に使用
- ダーク系テクスチャで深みを演出

---

## 8. Visual Style

- **写真**: 高品質な作品ポートフォリオ写真。ダーク背景に映えるよう彩度・コントラストが高めのものを選択
- **スライダー**: `slider-1.jpg` 〜 `slider-8.jpg` のヒーロービジュアル
- **アイコン**: 白い矢印SVG（右矢印・戻りアイコン）をナビゲーションやボタンに使用
- **テクスチャ**: 背景にパターンテクスチャを重ねて奥行きを演出

---

## 9. Do's and Don'ts

### Do（推奨）

- ダーク背景にアクセントカラーを効果的に使いコントラストを出す
- ポートフォリオ写真は品質最優先、種類と量でクリエイティビティを示す
- ボタンには矢印アイコンを添えてアクション方向を示す
- ローディング演出を丁寧に作り込む（最初の印象が重要）
- ワークフロー・プロセスを可視化して専門性をアピール

### Don't（禁止）

- 白背景（ブランドコンセプトと相反する）
- アクセントカラーを一度に全部使いすぎる（1セクション1〜2色まで）
- 写真品質の低いポートフォリオの掲載
- テキストの視認性が確保できない薄いグレーの多用

---

## 10. Responsive Behavior

### Breakpoints

| Name | Width | 説明 |
|------|-------|------|
| Mobile | ≤ 768px | 1カラム、スライダー縮小 |
| Tablet | ≤ 1024px | 2カラムグリッド |
| Desktop | > 1024px | フルレイアウト（2〜3カラム） |

### タッチターゲット

- 最小サイズ: 44px × 44px

### フォントサイズの調整

- モバイルでは本文 14–15px、大見出し（42px+）はデスクトップの 60〜70% に縮小

---

## 11. Agent Prompt Guide

### クイックリファレンス

```
Primary Background: #1e1e1e
Card Background: #2c2c2c
Text Color: #ffffff
Secondary Text: #aaaaaa
Accent Blue: #0057ff（推定）
Accent Orange: #ff6b35（推定）
Accent Green: #00b894（推定）
Accent Yellow: #fdcb6e（推定）
Font: "Noto Sans JP", "游ゴシック", Helvetica, sans-serif
Body Size: 16px
Line Height: 1.75
Design Style: ダーク・クリエイティブ・ポートフォリオ重視
```

### プロンプト例

```
stans.jpのデザインシステムに従って、プロジェクト一覧グリッドを作成してください。
- 背景: #1e1e1e（カード: #2c2c2c）
- テキスト: #ffffff（補足: #aaaaaa）
- フォント: "Noto Sans JP", sans-serif / 15px / line-height 1.75
- カード: スクエア・影なし・ホバーで輝度変化
- 3カラムグリッド、gutter 24px
- カード右下に白矢印アイコン付きリンク
- セクション間は 80–120px のスペース
- アクセントカラー（#0057ff 等）をカテゴリタグに使用
```
