# a4report theme

A4縦型・ドキュメントスタイルの Marp テーマ。

レポート・報告書・技術文書・インテリジェンスレポートなど、文字量の多い文書向けに設計している。  
[formal テーマ](../formal/) の配色（ティール × クリーム背景）を継承しつつ、A4縦・印刷重視の用途に再設計したテーマ。

## 特徴

- **A4縦サイズ** (794px × 1123px) — 印刷・PDF出力に適したサイズ
- **文書スタイル** — Word 的な上から順に書くレイアウト
- **TLP 対応** — TLP:CLEAR / GREEN / AMBER / RED を1行のクラス指定で切り替え可能
- **見出し H1〜H4** — サイズ統一・ボーダーで差別化
- **表紙ページ** (`class: title`) — タイトルを上1/3、メタ情報を右下に配置

## ファイル構成

```
marp-themes/a4report/
├── a4report.css    ← テーマ本体
├── README.md       ← このファイル
└── sample.md       ← 使用例
```

TLP 画像は `marp-themes/` 直下の PNG を GitHub raw コンテンツとして参照している。  
ローカルへの TLP 画像配置は不要。

## セットアップ

### VS Code (Marp for VS Code)

`.vscode/settings.json` にテーマのパスを追加する。

```json
{
  "markdown.marp.themes": [
    "./marp-themes/a4report/a4report.css"
  ]
}
```

GUI上から実施する場合は、以下の通り

1. VSCodeの設定を開く
2. 検索で`Marp Themes`を入力し、MarpのTheme設定を選択する
3. Themeの追加で `https://raw.githubusercontent.com/hogehuga/vulnRespStudyGroup/refs/heads/master/marp-themes/a4report/a4report.css`を追加する

### Marp CLI

```bash
marp --theme ./marp-themes/a4report/a4report.css document.md
```

## 基本的な使い方

```markdown
---
marp: true
theme: a4report
paginate: true
header: 作成組織名
footer: © 2025 作成者
---

<!-- class: tlp-clear -->

# 文書タイトル

本文テキスト...
```

`header:` / `footer:` ディレクティブは任意。設定した場合、ヘッダーは右揃え、フッターは左揃えで表示される（TLP 画像と反対側に配置されるため重ならない）。

## TLP の設定

`<!-- class: クラス名 -->` の1行だけで TLP ラベルが表示される。  
TLP 画像は左上・右下の2箇所に表示される。

| クラス名 | 表示される TLP | 区切り線 |
|:--|:--|:--|
| `tlp-none` | なし | — |
| `tlp-clear` | TLP:CLEAR | なし |
| `tlp-white` | TLP:WHITE (CLEAR 画像流用) | なし |
| `tlp-green` | TLP:GREEN | なし |
| `tlp-amber` | TLP:AMBER | なし |
| `tlp-red` | TLP:RED | なし |

```markdown
<!-- class: tlp-red -->
```

特定ページのみ変更したい場合はアンダースコア付きを使う。

```markdown
<!-- _class: tlp-amber -->
```

## 見出し

| 見出し | 用途 | スタイル |
|:--|:--|:--|
| `# H1` | 文書・大章タイトル | 太字・下線（ティール） |
| `## H2` | 大節 | 左ボーダー 5px + 薄背景 |
| `### H3` | 小節 | 左ボーダー 3px |
| `#### H4` | 項目見出し | 下点線 |

すべて 11pt で統一しており、サイズではなくボーダーと色で差別化している。

## 特殊クラス

### 表紙ページ (`title`)

タイトルをページ上1/3に中央揃えで表示し、本文テキストを右下に配置する。

```markdown
<!-- _class: title tlp-clear -->
<!-- _paginate: false -->

# 文書タイトル
## サブタイトル

作成組織名
2025年6月30日
著者名
```

- `# H1` — 太字・下線（タイトル）
- `## H2` — 通常ウェイト（サブタイトル）
- `p` — 右揃え・右下から上へ積み上げ（所属・日時・著者など）

### 文字詰めモード (`small`)

```markdown
<!-- _class: small -->
```

フォントサイズを 9pt に縮小し、要素間の余白を詰める。情報量の多いページで使用。

### ヘッダー区切り非表示 (`no-header`)

```markdown
<!-- _class: no-header -->
```

上区切り線とヘッダーを非表示にする。図表メインのページで使用。

### 反転カラー (`invert`)

```markdown
<!-- _class: invert -->
```

背景をダークグレー、文字をクリーム色に反転する。

## ページ番号

```markdown
---
marp: true
theme: a4report
paginate: true
---

<!-- _paginate: false -->
# 表紙（ページ番号なし）

---
# 本文（ページ番号あり）
```

ページ番号はスライド下中央に `N / Total` 形式で表示される。

## 注意事項

- **フォント** — Google Fonts (Noto Sans JP) をインターネット経由で読み込む。オフライン環境では `@import url(...)` 行を削除し、ローカルフォントに変更すること。
- **TLP 画像** — GitHub raw コンテンツを参照するため、インターネット接続が必要。ローカル運用する場合は CSS 内の URL をローカルパスに変更すること。
- **PDF 出力** — VS Code の Export Slide Deck → PDF、または `marp --pdf document.md` で出力できる。印刷時は「実際のサイズ」を選択すると A4 に正確に収まる。

## 関連

- [formal テーマ](../formal/) — 16:9 プレゼンテーション向けの姉妹テーマ
- [TLP 画像](../) — `marp-themes/` 直下の TLP-*.png を共有参照している
