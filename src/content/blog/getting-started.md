---
title: 'knitting_image_maker を使ってみよう'
description: 'インストールから最初の編み図画像生成までをステップごとに解説します。'
pubDate: '2026-05-07'
---

## knitting_image_maker とは

**knitting_image_maker** は、ニット編み図（棒針・かぎ針）のパターンを Python のコードで記述し、
PNG などの画像ファイルとして出力できる Python ライブラリです。

手書きや専用ソフトに頼らずに編み図を生成できるため、バージョン管理や自動化との相性が良いのが特徴です。

---

## インストール

Python 3.8 以上が必要です。pip でインストールできます。

```bash
pip install knitting-image-maker
```

依存ライブラリ（Pillow など）は自動的にインストールされます。

---

## 基本的な使い方

### 1. ライブラリをインポート

```python
from knitting_image_maker import KnittingChart
```

### 2. チャートを定義する

編み図は行列（リスト）で表します。各要素が 1 マスに対応します。

```python
# 記号の意味はライブラリのドキュメントを参照
pattern = [
    ['k', 'k', 'p', 'p', 'k', 'k'],
    ['p', 'p', 'k', 'k', 'p', 'p'],
    ['k', 'k', 'p', 'p', 'k', 'k'],
    ['p', 'p', 'k', 'k', 'p', 'p'],
]

chart = KnittingChart(pattern)
```

### 3. 画像を生成・保存

```python
chart.save('my_chart.png')
```

`my_chart.png` として編み図画像が保存されます。

---

## オプション

`KnittingChart` にはいくつかのオプションが用意されています。

| オプション | デフォルト | 説明 |
|-----------|-----------|------|
| `cell_size` | `40` | 1 マスのピクセルサイズ |
| `font_size` | `16` | 記号フォントのサイズ |
| `border_color` | `"#000000"` | マス目の枠線の色 |
| `background_color` | `"#ffffff"` | 背景色 |

例：マスを大きくして出力する

```python
chart = KnittingChart(pattern, cell_size=60)
chart.save('large_chart.png')
```

---

## 次のステップ

- 詳細な記号一覧は [GitHub リポジトリの README](https://github.com/KojiKobayashi/knitting_image_maker) を参照してください。
- Issue や Pull Request も歓迎しています。
