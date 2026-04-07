# DESIGN.md — weekday.co.jp

> 参考サイト: https://weekday.co.jp/
> 分析日: 2026-04-07
> 業種: デジタルファッション特化クリエイティブカンパニー コーポレートサイト（日本テレビグループ）

---

## 1. Visual Theme & Atmosphere

- **デザイン方針**: モダン・ラグジュアリー。ファッション業界の最先端性と、大手メディアグループのブランド信頼性を融合させた洗練されたデザイン
- **密度**: 中程度。事業領域ごとに明確に区切られたセクション型。ビジュアルと文章のバランスが取れている
- **キーワード**: ラグジュアリー、モダン、洗練、ファッション、デジタル

---

## 2. Color Palette & Roles

> 白背景×黒テキストのモノトーンベース。高級ファッションブランドと同様のカラー哲学で、写真とクライアントブランドの色彩が引き立つ設計。

### Primary（ブランドカラー）

- **Primary** (`#111111`): 見出し・ロゴ・主要テキストに使用する深い黒
- **Primary Dark** (`#000000`): ホバー・アクティブ状態

### Semantic（意味的な色）

- **Danger** (`#d32f2f`): エラー・削除
- **Warning** (`#f57c00`): 警告
- **Success** (`#388e3c`): 成功

### Neutral（ニュートラル）

- **Text Primary** (`#111111`): 本文テキスト
- **Text Secondary** (`#555555`): 補足情報・ラベル・キャプション
- **Text Disabled** (`#999999`): 非活性状態のテキスト
- **Border** (`#e8e8e8`): 区切り線・入力枠
- **Background** (`#ffffff`): ページ全体の背景（純白）
- **Surface** (`#f9f9f9`): カード・セクション背景の薄いグレー

---

## 3. Typography Rules

### 3.1 和文フォント

- **ゴシック体**: Adobe Fonts (Typekit) 経由。グロテスク系または現代的ゴシック（例: A1ゴシック, じゅん101）

### 3.2 欧文フォント

- **サンセリフ**: Adobe Fonts 経由。エレガントなサンセリフ（例: Futura, Neue Haas Grotesk, Söhne 等のモダン系）
- 大型見出し "A Creative Pivot to Connect with the Digital Fashion Heartbeat" から、欧文にも特別なフォントを採用していることが確認できる

### 3.3 font-family 指定（推定）

```css
/* 本文 */
font-family: "Adobe Gothic", "游ゴシック", "Yu Gothic", Helvetica, sans-serif;

/* 英語見出し・ディスプレイ */
font-family: "Futura PT", "Helvetica Neue", Arial, sans-serif;
```

### 3.4 文字サイズ・ウェイト階層

| Role | Font | Size | Weight | Line Height | Letter Spacing | 備考 |
|------|------|------|--------|-------------|----------------|------|
| Display | 欧文サンセリフ | 60–80px | 300–400 | 1.1 | -0.02em | 英語ヒーローコピー |
| Heading 1 | ゴシック/欧文 | 36–48px | 400 | 1.25 | 0.02em | セクション大見出し |
| Heading 2 | ゴシック | 24–32px | 400 | 1.4 | 0.02em | サブ見出し |
| Heading 3 | ゴシック | 18–22px | 500 | 1.5 | 0.01em | 小見出し |
| Body | ゴシック | 15–16px | 400 | 1.8 | 0.03em | 本文 |
| Caption | ゴシック | 12–13px | 400 | 1.6 | 0.04em | 補足・注釈 |

### 3.5 行間・字間

- **本文の行間 (line-height)**: 1.7〜1.9
- **見出しの行間**: 1.1〜1.3（大きい欧文ディスプレイは 1.0〜1.1）
- **本文の字間 (letter-spacing)**: 0.03em
- **欧文見出しの字間**: -0.02〜0em（詰め気味でラグジュアリー感）

### 3.6 禁則処理・改行ルール

```css
word-break: break-all;
overflow-wrap: break-word;
line-break: strict;
```

### 3.7 OpenType 機能

```css
/* 見出し・ナビゲーション */
font-feature-settings: "palt" 1, "kern" 1;

/* 欧文ディスプレイ */
font-feature-settings: "kern" 1, "liga" 1;
```

### 3.8 縦書き

該当なし

---

## 4. Component Stylings

### Buttons

**Primary**
- Background: `#111111`
- Text: `#ffffff`
- Padding: 14px 36px
- Border Radius: 0px（スクエア）
- Font Size: 13–14px
- Letter Spacing: 0.1em（大文字スペーシング）

**Secondary（"view more" 型）**
- Background: `transparent`
- Text: `#111111`
- Border: 1px solid `#111111`
- Padding: 12px 32px
- Border Radius: 0px

### Cards（実績・メディア一覧）

- Background: `#ffffff`
- Border: なし or `1px solid #e8e8e8`
- Border Radius: 0px（スクエア）
- Padding: 0px（画像エッジトゥエッジ） + テキストエリア 16–24px
- Shadow: なし

### Navigation（グローバルナビ）

- 項目: 事業・サービス / 事例・実績 / 会社情報 / 採用情報
- スタイル: 水平テキストメニュー、黒文字
- ロゴ: 左上配置
- ホバー: アンダーライン or 色変化
- モバイル: ハンバーガーメニュー

### Media Slider（Droptokyo / The Fashion Post / ANOTHER SKY）

- JavaScript駆動のカルーセル型スライダー
- 矢印またはドットナビゲーション

---

## 5. Layout Principles

### Spacing Scale

| Token | Value |
|-------|-------|
| XS | 8px |
| S | 16px |
| M | 32px |
| L | 64px |
| XL | 96px |
| XXL | 128px |

### Container

- Max Width: 1280px
- Padding (horizontal): 48–80px

### Grid

- Columns: 12カラム
- Gutter: 24–32px
- 事業領域: 2カラム（テキスト＋ビジュアル）
- メディア一覧: 3カラムのカードグリッド

### セクション構成

1. **Hero** — 大型欧文コピー + ビジュアル（"A Creative Pivot to Connect with the Digital Fashion Heartbeat"）
2. **事業領域** — 4つのサービス（メディア / クリエイティブスタジオ / デジタルマーケティング / TV番組プロデュース）
3. **メディアスライダー** — Droptokyo / The Fashion Post / ANOTHER SKY
4. **クライアント一覧** — Louis Vuitton, Gucci, Chanel 等のロゴ列挙
5. **実績・事例** — カードグリッド
6. **会社情報・採用** — テキストセクション
7. **Footer** — ナビゲーション・コピーライト

---

## 6. Depth & Elevation

| Level | Shadow | 用途 |
|-------|--------|------|
| 0 | none | 主要要素（フラット基本） |
| 1 | `0 2px 8px rgba(0,0,0,0.08)` | カードホバー時 |

---

## 7. Animation & Interaction

- **スピナー**: ページロード時の表示
- **カードホバー**: 画像のスケールアップ or テキストオーバーレイ
- **メディアスライダー**: JavaScriptによる動的スライド（自動再生 or 手動）
- **スクロール連動**: 要素のフェードイン（opacity + translateY）
- **ナビゲーション**: スクロール時の背景色変化（透過→白）

---

## 8. Visual Style

- **写真**: Droptokyo・The Fashion Post・ANOTHER SKY などのファッションメディア写真。高解像度・スタイリッシュなエディトリアル撮影
- **クライアントロゴ**: Louis Vuitton / Gucci / Chanel 等のブランドロゴをグレースケールで一覧表示（権威性の可視化）
- **アイコン**: 矢印・スライダーナビゲーション用のシンプルSVG

---

## 9. Do's and Don'ts

### Do（推奨）

- 欧文の大型ディスプレイタイポグラフィでインパクトを出す
- クライアントブランドのロゴを早い段階で見せる（信頼性の確立）
- 実績写真はエディトリアル品質のものを使用
- 事業領域を明確に区分し、ユーザーが興味のある領域に誘導する
- モノトーンベースで、写真の色彩を最大限に活かす

### Don't（禁止）

- カラフルなアクセントカラーの多用
- 過剰な装飾・グラデーション（ファッション業界の洗練さを損なう）
- 情報の混在（メディア・スタジオ・マーケ・TVを同一セクションに詰め込まない）
- クライアントブランドのガイドライン違反になる使い方

---

## 10. Responsive Behavior

### Breakpoints

| Name | Width | 説明 |
|------|-------|------|
| Mobile | ≤ 768px | 1カラム、大型テキスト縮小 |
| Tablet | ≤ 1024px | 2カラム |
| Desktop | > 1024px | フルレイアウト（12カラム） |

### タッチターゲット

- 最小サイズ: 44px × 44px

### フォントサイズの調整

- モバイルでは欧文ディスプレイ 36–44px、本文 14–15px に調整

---

## 11. Agent Prompt Guide

### クイックリファレンス

```
Primary Color: #111111
Text Color: #111111
Secondary Text: #555555
Background: #ffffff
Surface: #f9f9f9
Font (本文): "Adobe Gothic", "游ゴシック", Helvetica, sans-serif
Font (欧文見出し): "Futura PT", "Helvetica Neue", sans-serif
Body Size: 15–16px
Line Height: 1.8
Design Style: モダン・ラグジュアリー・ファッション特化
```

### プロンプト例

```
weekday.co.jpのデザインシステムに従って、事業紹介セクションを作成してください。
- 背景: #ffffff
- テキスト: #111111（補足: #555555）
- 欧文見出しフォント: "Helvetica Neue", sans-serif / 太さ: 300–400 / 文字間隔: -0.02em
- 本文フォント: "游ゴシック", sans-serif / 15px / line-height 1.8
- カードは影なし・スクエア・2カラムレイアウト
- "view more" ボタン: アウトライン型（border 1px solid #111111）
- セクション間は 96–128px のスペース
- クライアントロゴはグレースケールで横一列に並べる
```
