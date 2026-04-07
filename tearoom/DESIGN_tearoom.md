# DESIGN.md — tearoom.co.jp

> 参考サイト: https://tearoom.co.jp/
> 分析日: 2026-04-07
> 業種: 茶文化・産業融合型スタートアップ コーポレートサイト

---

## 1. Visual Theme & Atmosphere

- **デザイン方針**: 「対立のない優しい世界を目指して」という理念を体現した、静謐で格調高い日本美学ベースのデザイン。茶文化の伝統的な美意識と現代的なビジネス感覚を融合
- **密度**: 低〜中。余白を重視した読みやすいエディトリアルレイアウト。テキストによるストーリーテリングを重視
- **キーワード**: 静謐、格調、茶、日本美、対話、誠実

---

## 2. Color Palette & Roles

> 茶文化を想起させるアースカラー・和の色彩がベース。白・抹茶グリーン・茶色系のナチュラルパレット。

### Primary（ブランドカラー）

- **Primary** (`#2d4a3e`推定): 深い抹茶グリーン系 — 茶文化を象徴するメインカラー
- **Primary Dark** (`#1a2e26`推定): ホバー・強調時のより深いグリーン

### Secondary（サブカラー）

- **Brown** (`#6b4c3b`推定): 茶褐色 — 茶器・土の色。アクセントや見出しに
- **Beige** (`#f0e9dc`推定): 和紙のようなベージュ — セクション背景

### Semantic（意味的な色）

- **Danger** (`#c0392b`): エラー（使用は最小限）
- **Warning** (`#e67e22`): 警告（使用は最小限）
- **Success** (`#27ae60`): 成功（使用は最小限）

### Neutral（ニュートラル）

- **Text Primary** (`#1a1a1a`): 本文テキスト（深い濃い色）
- **Text Secondary** (`#666666`): 補足テキスト・キャプション
- **Text Disabled** (`#aaaaaa`): 非活性状態
- **Border** (`#d9cfc4`推定): 和紙調のソフトなボーダー
- **Background** (`#faf8f5`推定): わずかに温かみのあるオフホワイト（和紙色）
- **Surface** (`#f0e9dc`推定): ベージュ系のカード・セクション背景

---

## 3. Typography Rules

### 3.1 和文フォント

- **ゴシック体**: Noto Sans JP（本文・UI要素）
- **明朝体**: Noto Serif JP または游明朝（見出し・キャッチ。茶文化の格調を表現するために明朝体を積極使用）

### 3.2 欧文フォント

- **サンセリフ**: Helvetica Neue または Inter（補助的に使用）
- **セリフ**: EB Garamond 等のクラシカルセリフ（欧文見出しに使用の可能性）

### 3.3 font-family 指定（推定）

```css
/* 本文 */
font-family: "Noto Sans JP", "游ゴシック", "Yu Gothic", sans-serif;

/* 見出し・格調テキスト */
font-family: "Noto Serif JP", "游明朝", "Yu Mincho", serif;

/* 欧文アクセント */
font-family: "EB Garamond", Georgia, serif;
```

### 3.4 文字サイズ・ウェイト階層

| Role | Font | Size | Weight | Line Height | Letter Spacing | 備考 |
|------|------|------|--------|-------------|----------------|------|
| Display | 明朝体 | 48–64px | 300–400 | 1.3 | 0.1em | ヒーローキャッチ（間を大きく） |
| Heading 1 | 明朝体 | 32–44px | 400 | 1.4 | 0.08em | 大見出し（哲学・理念） |
| Heading 2 | ゴシック/明朝 | 22–28px | 400 | 1.5 | 0.05em | セクション見出し |
| Heading 3 | ゴシック | 16–20px | 500 | 1.6 | 0.04em | 小見出し |
| Body | ゴシック | 15–16px | 400 | 2.0–2.2 | 0.05em | 本文（ゆったりした行間） |
| Caption | ゴシック | 12–13px | 400 | 1.7 | 0.06em | 補足・注釈 |

### 3.5 行間・字間

- **本文の行間 (line-height)**: 2.0〜2.2（茶道の「間」を意識した広い行間）
- **見出しの行間**: 1.3〜1.5
- **本文の字間 (letter-spacing)**: 0.05em（日本語らしい落ち着きのある字間）
- **見出しの字間**: 0.08〜0.12em（格調を高めるために広めに設定）

### 3.6 禁則処理・改行ルール

```css
word-break: break-all;
overflow-wrap: break-word;
line-break: strict;
```

### 3.7 OpenType 機能

```css
/* 見出し・格調テキスト */
font-feature-settings: "palt" 1, "kern" 1;

/* 明朝体の見出し */
font-feature-settings: "palt" 1;
```

### 3.8 縦書き

```css
/* 縦書き対応の可能性あり（茶道・日本美学のテーマ） */
writing-mode: vertical-rl;
text-orientation: mixed;
```

日本文化を強調するセクションでの縦書き使用を検討

---

## 4. Component Stylings

### Buttons

**Primary（格調型）**
- Background: `#2d4a3e`（深い抹茶グリーン）
- Text: `#ffffff`
- Padding: 14px 40px
- Border Radius: 0px（茶道の「直線美」）
- Letter Spacing: 0.15em（格調ある字間）

**Secondary（アウトライン型）**
- Background: `transparent`
- Text: `#2d4a3e`
- Border: 1px solid `#2d4a3e`
- Padding: 12px 36px
- Border Radius: 0px

**テキストリンク**
- Color: `#2d4a3e`（または `#6b4c3b`）
- Hover: アンダーライン

### Cards（Dialogueコンテンツ等）

- Background: `#faf8f5` or `#f0e9dc`（ベージュ系）
- Border: 1px solid `#d9cfc4`（和紙調）
- Border Radius: 0px
- Padding: 32–48px
- Shadow: なし

### Navigation

- 項目: Philosophy / Business Story / Dialogue / 採用情報 / Contact（推定）
- スタイル: シンプルな水平テキストメニュー
- カラー: 白（または和紙色）背景に濃いテキスト
- ロゴ: 左上または中央

---

## 5. Layout Principles

### Spacing Scale

| Token | Value |
|-------|-------|
| XS | 8px |
| S | 16px |
| M | 32px |
| L | 64px |
| XL | 104px |
| XXL | 144px |

### Container

- Max Width: 1120–1280px
- Padding (horizontal): 40–80px
- テキストカラム幅: 最大 720px（長文の可読性を確保）

### Grid

- Columns: 12カラム（デスクトップ）
- Gutter: 32px
- Dialogue・記事系: 1カラム（テキスト中心）
- Business Story: 2カラム（テキスト＋ビジュアル）

### セクション構成

1. **Hero** — 茶の世界観を表す静的ビジュアル + キャッチコピー
2. **Philosophy** — 「対立のない優しい世界を目指して」の理念説明
3. **Business Story** — 事業内容説明（テキスト＋ビジュアル）
4. **Dialogue** — ステークホルダーとの対話インタビュー
5. **採用情報** — 採用メッセージ
6. **Footer** — 会社情報・コピーライト

---

## 6. Depth & Elevation

| Level | Shadow | 用途 |
|-------|--------|------|
| 0 | none | 主要要素（完全フラット） |
| 1 | `0 2px 8px rgba(0,0,0,0.06)` | カード（使用は控えめ） |

---

## 7. Animation & Interaction

- **方針**: 最小限・上品なアニメーション。茶道の「静」の美学を尊重
- **フェードイン**: opacity のみのシンプルなスクロール連動フェード（0.8〜1.2秒）
- **ページ遷移**: フェードのみ（スライドやバウンスは使用しない）
- **ホバー**: 微細な色変化（スケールアップは行わない）

---

## 8. Visual Style

- **写真**: 茶室・茶器・お茶・自然を撮影した高品質な写真。和のトーンで統一（暖色系、落ち着いた彩度）
- **写真スタイル**: 余白を残した構図（日本美学の「間」）、自然光を活かした柔らかい照明
- **テキスト重視**: 写真とテキストが対等に重要。インタビュー・対話コンテンツは長文
- **アイコン**: 最小限のSVGアイコン（矢印・SNSのみ）

---

## 9. Do's and Don'ts

### Do（推奨）

- 明朝体を見出しに積極的に使い、日本的な格調を演出する
- 行間・字間を広めにとり、「間」の美学を体現する
- 写真は「引き算の美学」で選ぶ（余白のある構図を優先）
- テキストコンテンツ（対話・インタビュー）を重視したレイアウト
- ベージュ・和紙色の背景で温かみと格調を表現

### Don't（禁止）

- 高彩度・現代的なアクセントカラーの多用（茶の世界観と相反する）
- 速い・激しいアニメーション（静謐さを損なう）
- 欧米的なモダンデザインの過剰な採用
- テキストを短くし過ぎた情報断片化（対話・物語を大切にする）
- 余白のない詰め込み型レイアウト

---

## 10. Responsive Behavior

### Breakpoints

| Name | Width | 説明 |
|------|-------|------|
| Mobile | ≤ 768px | 1カラム、縦書き要素は横書きに切り替え |
| Tablet | ≤ 1024px | 1〜2カラム |
| Desktop | > 1024px | フルレイアウト |

### タッチターゲット

- 最小サイズ: 44px × 44px

### フォントサイズの調整

- モバイルでは本文 14–15px（line-height は維持: 2.0）
- 見出し明朝体はデスクトップの 65〜75% に縮小

---

## 11. Agent Prompt Guide

### クイックリファレンス

```
Primary Color: #2d4a3e（深い抹茶グリーン）
Secondary Color: #6b4c3b（茶褐色）
Text Color: #1a1a1a
Secondary Text: #666666
Background: #faf8f5（和紙調オフホワイト）
Surface: #f0e9dc（ベージュ）
Border: #d9cfc4
Font (本文): "Noto Sans JP", "游ゴシック", sans-serif
Font (見出し): "Noto Serif JP", "游明朝", serif
Body Size: 15–16px
Line Height: 2.1
Letter Spacing (本文): 0.05em
Design Style: 日本美学・茶文化・静謐・格調
```

### プロンプト例

```
tearoom.co.jpのデザインシステムに従って、Philosophyセクションを作成してください。
- 背景: #faf8f5（和紙調）
- テキスト: #1a1a1a（補足: #666666）
- 見出しフォント: "Noto Serif JP", serif / 36px / weight 400 / letter-spacing 0.08em
- 本文フォント: "Noto Sans JP", sans-serif / 16px / line-height 2.1 / letter-spacing 0.05em
- セクション最大幅: 720px（テキスト可読性重視）
- セクション間: 104–144px のホワイトスペース
- ボタン: 抹茶グリーン (#2d4a3e) の角ばったボタン
- アニメーション: opacity フェードイン のみ（ゆっくり 1.0秒）
```
