---
title: HTMLOListElement
slug: Web/API/HTMLOListElement
---
{{ APIRef("HTML DOM") }}

**`HTMLOListElement`** インターフェイスは、（継承によって使用できる通常の {{domxref("HTMLElement")}} インターフェイスのものに加えて）順序付きリスト要素を操作するための特別なプロパティを提供します。

{{InheritanceDiagram}}

## プロパティ

_親である {{domxref("HTMLElement")}} からプロパティを継承しています。_

- {{domxref("HTMLOListElement.reversed")}}
  - : 論理値で {{htmlattrxref("reversed", "ol")}} を反映しており、番号が降順なるのであれば値が `true` を、昇順になるのであれば `false` を定義します。
- {{domxref("HTMLOListElement.start")}}
  - : `long` 型の値で {{htmlattrxref("start", "ol")}} を反映しており、リストの最初の要素の最初の番号の値を定義します。
- {{domxref("HTMLOListElement.type")}}

  - : 文字列で {{htmlattrxref("type", "ol")}} を反映しており、表示に使用するマーカーの種類を定義します。以下の値を取ることができます。

    - `'1'` は数字が使用されることを意味します。例: `1`, `2`, `3`, `4`, `5`, …
    - `'a'` は小文字のラテンアルファベットが使用されることを意味します。例:  `a`, `b`, `c`, `d`, `e`, …
    - `'A'` は大文字のラテンアルファベットが使用されることを意味します。例: `A`, `B`, `C`, `D`, `E`, …
    - `'i'` は小文字のラテン数字が使用されることを意味します。例: `i`, `ii`, `iii`, `iv`, `v`, …
    - `'I'` は大文字のラテン数字が使用されることを意味します。例: `I`, `II`, `III`, `IV`, `V`, …

- {{domxref("HTMLOListElement.compact")}} {{deprecated_inline}}
  - : 論理値で、リスト項目間の間隔を縮小すべきであることを示します。このプロパティは {{htmlattrxref("compact", "ol")}} 属性を反映するのみで、最近のページでは、その動作に使用される CSS の {{cssxref("line-height")}} プロパティは考慮されません。

## メソッド

_固有のメソッドはありません。親である {{domxref("HTMLElement")}} からメソッドを継承しています。_

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- このインターフェイスを実装している HTML 要素: {{ HTMLElement("ol") }}
