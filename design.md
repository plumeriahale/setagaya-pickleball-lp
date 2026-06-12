# 世田谷ピックルボール連盟 — デザインシステム v2.0

> *"Confidence through minimalism."*

作成：Chief Design Architect  
バージョン：2.0 | 2026-05-07  
前バージョン：1.0（廃止）

---

## 00. プロジェクト定義

### ビジョン
「世田谷発、次世代アーバンスポーツカルチャーのデジタル旗艦」

これは地域スポーツ連盟のウェブサイトではない。  
Nike、Apple、Monocle と同じ棚に並べられるべき、**スポーツ文化ブランドの体験プラットフォーム**だ。

### このサイトが「ある」もの
- 次世代型アーバンスポーツ文化プラットフォーム
- 現代的なコミュニティブランド
- シネマティックなデジタル体験

### このサイトが「ない」もの
- 行政的な地域連盟サイト
- PDFアーカイブ
- テキスト過多のフェデレーションサイト

### ユーザーが感じるべきエモーション
```
❌  "ここに情報があります"
✅  "私もこのコミュニティに加わりたい"
```

---

## 01. デザイン原則

### 四原則

```
1. MINIMALISM    — 削れるものはすべて削る
2. QUIET LUXURY  — 品格は静けさの中にある
3. MOBILE FIRST  — モバイルが主役。PCは拡張
4. HUMAN EMOTION — データより感情を動かせ
```

### インスピレーション源
| ブランド | 学ぶもの |
|---------|---------|
| Apple | 情報密度の制御、タイポグラフィの権威 |
| Nike | スポーツの本質を伝える映像言語 |
| Aesop | 静けさとブランドへの信頼構築 |
| Monocle | エディトリアルな視点とグローバルな品格 |
| FIFA+ | スポーツコンテンツのシネマティック表現 |

---

## 02. カラーシステム

### プライマリーパレット

```
Primary     #111111    ─── テキスト・暗い背景
Background  #FFFFFF    ─── メイン背景
Accent      #D9FF3F    ─── CTA・ハイライト（使用量 ≤ 8%）
Alt Accent  #3B82F6    ─── セカンダリアクセント（使用量 ≤ 5%）
```

### セマンティックトークン

```css
--c-primary:    #111111;
--c-bg:         #FFFFFF;
--c-accent:     #D9FF3F;
--c-blue:       #3B82F6;
--c-muted:      #888888;
--c-subtle:     #F2F2F0;  /* セクション背景 */
--c-dark:       #0A0A0A;  /* ヒーロー背景 */
--c-border:     #E5E5E5;
```

### アクセントカラーの使用ルール

```
✅ CTAボタン（Primary）
✅ 数字・統計のハイライト
✅ スクロールインジケーター
✅ バッジ・タグ
❌ 見出しテキスト全体
❌ 背景の広い面積
❌ 複数の要素に同時使用
```

### コントラスト要件（WCAG AA準拠）

| 組合せ | Contrast Ratio | 判定 |
|--------|---------------|------|
| #111111 on #FFFFFF | 18.1:1 | ✅ Pass |
| #888888 on #FFFFFF | 3.9:1 | ✅ Pass (Large) |
| #D9FF3F on #111111 | 11.2:1 | ✅ Pass |
| #FFFFFF on #111111 | 18.1:1 | ✅ Pass |

---

## 03. タイポグラフィ

### フォントファミリー

```
日本語:  Noto Sans JP  (Google Fonts)
英語:    Inter         (Google Fonts)
```

両フォントはワードマークからキャプションまでシステム全体で統一。  
mixing は最小限に。ページ内で2フォントを超えない。

### タイプスケール

```
Display     clamp(52px, 8.5vw, 112px)  weight:900  tracking:-0.045em  lh:0.92
Hero JP     clamp(40px, 6.5vw, 88px)   weight:900  tracking:-0.02em   lh:1.05
H1          clamp(36px, 5vw, 64px)     weight:800  tracking:-0.03em   lh:1.1
H2          clamp(28px, 3.5vw, 48px)   weight:700  tracking:-0.02em   lh:1.15
H3          clamp(20px, 2vw, 26px)     weight:700  tracking:-0.01em   lh:1.2
Body L      clamp(16px, 1.5vw, 20px)   weight:400               lh:1.9
Body        16px                       weight:400               lh:1.75
Caption     12px                       weight:500  tracking:0.04em
Label       10–11px                    weight:700  tracking:0.12em  uppercase
```

### 日本語タイポグラフィの原則

```
1. 大見出しは font-weight: 900 を使う（900がない場合は700）
2. 本文は weight: 400 のみ。bold多用は禁止
3. letter-spacing は -0.02em（見出し）〜 0em（本文）
4. 行間 (line-height) 本文は 1.8–2.0 を基本とする
5. 1行あたりの文字数: 本文は最大 38文字（モバイル）
```

---

## 04. スペーシングシステム

```
--section-y:  clamp(80px, 10vw, 140px)   /* セクション間垂直余白 */
--pad-x:      clamp(20px, 5vw, 72px)     /* 水平パディング */
--max-w:      1280px                     /* コンテンツ最大幅 */
```

### 8px グリッド

すべての間隔は 8px の倍数を基本とする:  
`4 / 8 / 12 / 16 / 24 / 32 / 40 / 48 / 64 / 80 / 96 / 120 / 160`

---

## 05. サイト構成

```
/
├── / ─────── Home（本ドキュメントの主対象）
├── /about ── 連盟について
├── /play ─── プレーガイド
├── /events ─ イベント一覧・詳細
├── /community コミュニティ
├── /partners  パートナー
└── /contact ─ お問い合わせ
```

**設計原則：フラット構造・深さ2階層まで**

---

## 06. ページ構成（ホームページ）

### ▌NAV（固定）
- 高さ: 64px
- ヒーロー時: 透明（テキスト白）
- スクロール後: white/88% + backdrop-blur(16px)
- 要素: ロゴ | Links | 言語トグル | CTA
- モバイル: ハンバーガーメニュー

### ▌01 HERO（Fullscreen）
- 高さ: `100svh`（Safe View Height）
- 背景: ダーク + グレイン + コートラインSVG（装飾）
- 構成: Eyebrow → 日本語H1 → 英語サブ → CTAトリプル
- ヘッドライン: `都市に、新しいスポーツ文化を。`
- スクロールインジケーター: 右下固定

### ▌02 STATS BAR
- 背景: #111111
- 4カラムグリッド
- 数字: Inter 800 + D9FF3F
- Gap: 1px（ダーク背景で区切り線に見える）

### ▌03 WHAT IS PICKLEBALL
- レイアウト: 大見出し → 4列フィーチャーカード
- Display text: `EASY TO START. HARD TO STOP.`
- フィーチャーカード: アイコン + 英題 + 日本語サブ + 説明文

### ▌04 COMMUNITY
- 横スクロールギャラリー（ドラッグ可）
- 見出し: `PLAY TOGETHER. / CONNECT NATURALLY.`
- カード高さに変化をつけてリズムを作る

### ▌05 EVENTS
- 背景: #111111
- Appleスタイルのリスト表示
- 構成: 日付(大) | イベント名 + バッジ + 会場 | Entry CTA
- カラーバッジで難易度表現

### ▌06 PHILOSOPHY
- 背景: #F2F2F0（subtle）
- 2カラム: 大見出し + テキスト&タグ
- ヘッドライン: `"We believe sports create cities."`

### ▌07 BEGINNERS
- 2カラム: テキスト + 暗いビジュアルボックス
- 心理設計: welcome / safe / relaxed（競争感ゼロ）
- CTA: `体験会に申し込む →`

### ▌08 PARTNERS
- モノクロームロゴテキスト
- 「スポンサー」でなく「文化的コラボレーター」のトーン

### ▌FOOTER
- 2カラム: ブランド + ナビ3列
- SNSリンク
- コピーライト

---

## 07. コンポーネント仕様

### ボタン

```
.btn-primary
  bg: D9FF3F  |  color: #111111  |  radius: 100px
  padding: 14px 28px  |  font: JP 14px 700
  hover: bg #C5F020 + translateY(-2px) + shadow

.btn-ghost
  border: 1px solid rgba(255,255,255,0.18)
  color: rgba(255,255,255,0.6)  |  radius: 100px
  hover: border-opacity↑ + color white

.btn-dark
  bg: #111111  |  color: white
  hover: bg #333 + translateY(-2px)
```

### バッジ

```
--green:  bg rgba(D9FF3F, 0.12) / color D9FF3F
--blue:   bg rgba(3B82F6, 0.15) / color #60A5FA
--white:  bg rgba(fff, 0.10)   / color rgba(fff, 0.5)
```

### カード（フィーチャー）

```
background: #FFFFFF
hover: background #FAFAF8
transition: 0.25s
padding: clamp(24px, 3vw, 40px)
border: none（グリッドギャップで区切り）
```

### ナビゲーション言語トグル

```
平常時:  bg rgba(fff, 0.12) / 半透明
Active: bg white / color #111
スクロール後: bg --c-subtle / Active: bg #111 / color white
```

---

## 08. モーション設計

### Easing Tokens

```css
--ease-out:    cubic-bezier(0.0, 0.0, 0.2, 1.0);  /* 標準 */
--ease-in-out: cubic-bezier(0.4, 0.0, 0.2, 1.0);  /* スムース */
```

### 使用するモーション

```
Scroll Reveal   : opacity 0→1 + translateY(18px→0) / 0.75s ease-out
Hero Stagger    : 各要素 0.15s ずつ遅延して登場
Hover (Button)  : translateY(-2px) + shadow / 0.15s
Hover (Card)    : background change / 0.25s
Scroll Pulse    : スクロールインジケーターの点滅アニメ
```

### 禁止事項

```
❌ bounce / spring effects
❌ rotate / scale transformations
❌ 連続するアニメーション（1要素に複数同時）
❌ duration > 600ms
❌ gaming aesthetic な演出
```

### Accessibility

```css
@media (prefers-reduced-motion: reduce) {
  /* すべてのアニメーションを即時完了状態に */
}
```

---

## 09. レスポンシブ設計

### ブレークポイント

```
Mobile   : 0 – 767px
Tablet   : 768 – 1023px
Desktop  : 1024px –
Max-width: 1280px（水平センタリング）
```

### モバイルでの変更点

```
features grid     : 4col → 1col
beginners inner   : 2col → 1col
philosophy inner  : 2col → 1col
nav links         : hidden → hamburger
event-row cta     : hidden（タップ = 詳細へ）
stats inner       : 4col → 2col
footer main       : 2col → 1col
```

### clamp() 優先設計

固定pxは使わない。すべてのサイズは `clamp(min, preferred, max)` で流動的に。

---

## 10. テックスタック

```
Framework  : Next.js (App Router) / TypeScript
Styling    : TailwindCSS（本プロトタイプはVanilla CSSで実装）
Animation  : Framer Motion（Scroll + Page transitions）
CMS        : Sanity CMS（非技術スタッフが更新可能）
Hosting    : Vercel
Images     : Next.js Image（WebP自動変換 / Lazy load）
Fonts      : Google Fonts（next/font で最適化）
Forms      : Sanity + Vercel Functions
```

### Sanity スキーマ（必須）

```
Event    { title, titleEn, date, level, venue, venueMap, entryUrl }
News     { title, body, publishedAt, image }
Member   { name, role, photo }
Partner  { name, logo, url, category }
```

---

## 11. パフォーマンス目標

| 指標 | 目標 |
|------|------|
| Lighthouse Performance | ≥ 95 |
| LCP | ≤ 2.5s |
| INP | ≤ 100ms |
| CLS | ≤ 0.05 |
| Total Bundle (JS) | ≤ 150KB gzip |

### 最適化チェックリスト

```
☐ next/font でフォント最適化（FOUT除去）
☐ 全画像 WebP + srcset + sizes
☐ Hero動画: WebM / 3MB以下 / autoplay muted loop
☐ Critical CSS: インライン
☐ 不要な JS: tree-shake + dynamic import
☐ Vercel Edge Network: 全アセット CDN配信
```

---

## 12. SEO

### 重点キーワード

```
日本語: 世田谷 ピックルボール / 東京 ピックルボール / ピックルボール 初心者 東京
英語:   Setagaya Pickleball / Tokyo Pickleball / Beginner Pickleball Tokyo
```

### セマンティック構造

```html
<h1> ─ ページに1つのみ
<h2> ─ 各セクション見出し
<article> ─ イベントカード
<nav aria-label="...">
<section aria-labelledby="...">
```

---

## 13. アクセシビリティ

```
✅ WCAG 2.1 AA コントラスト準拠
✅ キーボードナビゲーション（Tab / Enter / Esc）
✅ フォーカスリングの視覚的表示
✅ aria-label / aria-pressed / role 属性
✅ prefers-reduced-motion サポート
✅ alt テキスト（全画像）
✅ lang 属性（言語切替時に更新）
✅ Skip to Content リンク（開発フェーズで追加）
```

---

## 14. 二言語対応

### 要件

```
- URL ルーティング: /ja/* と /en/* で分離（またはi18n middleware）
- 言語トグル: ナビバーに常時表示
- 翻訳品質: 機械翻訳禁止。ネイティブコピーライター使用
- 日本語: Noto Sans JP で美しく。英語: Inter で洗練に
```

### コピーライティング原則

```
日本語: 詩的・簡潔・体言止め多用
英語:   Editorial tone / Active voice / No jargon
```

---

## 15. 開発フェーズ

### Phase 1（MVP）

```
☐ ホームページ（本プロトタイプ）
☐ イベント一覧・詳細ページ
☐ 初心者ガイドページ
☐ コンタクトフォーム
☐ Instagram フィード統合
☐ 二言語対応（JP/EN）
```

### Phase 2（Growth）

```
☐ メンバーランキング
☐ コーチ一覧・プロフィール
☐ コート予約システム
☐ 試合ライブストリーミング
☐ メンバーポータル（ログイン）
```

---

## 16. 写真・ビジュアルガイドライン

### 使うもの

```
✅ 実際のコートでの自然な撮影
✅ 自然光（ゴールデンアワー歓迎）
✅ 多様な年齢・国籍・背景
✅ 笑顔が生まれている「瞬間」
✅ アーバンな背景（都市感）
```

### 使わないもの

```
❌ AI生成写真（リアリティが命）
❌ 無理に作った笑顔
❌ 古いスポーツ写真のスタイル
❌ 式典・表彰式の写真（動きがない）
❌ 暗いフィルター・過度なレタッチ
```

### 技術仕様

```
Format   : WebP (fallback: JPEG)
Max size : 200KB / 1枚（Hero動画: 3MB）
Aspect   : Hero 16:9 / Cards 4:3 / Gallery 自由
Alt text : 必須（内容を説明、装飾的なものは alt=""）
```

---

## 17. デザイン判断のチェックリスト

何か追加・変更しようとするとき、この問いに答えよ：

```
□ これを削除したらサイトが成立しないか？
□ ユーザーを「入りたい」と思わせるか？
□ スマートフォンで美しいか？
□ Apple のサイトに並べて恥ずかしくないか？
□ アクセシビリティ要件を満たすか？
```

5問すべてに Yesが出なければ、実装しない。

---

> **最終メモ：**
>
> 「次世代アーバンスポーツカルチャー」は言葉で作るものじゃない。
> デザインの一画素、コピーの一単語、写真の一瞬が、
> その世界観を証明する。
>
> このサイトは、世田谷のコートの空気をデジタルに変換するものだ。
> それ以上でも、それ以下でもない。

---
*SPF Design System v2.0 / © 2026 世田谷ピックルボール連盟*
