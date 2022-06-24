---
layout: post
title: "Dartのコーディングルールまとめ"
categories: dart
tags: "Dart" "Flutter" "Coding"
---

# 〇〇ケースとは
以後，「アッパーキャメルケース」のような「〇〇ケース」という言葉が多く出てきます．まずはそれについて説明しておきます．

そもそもプログラミングにおいて，変数や関数などには**それが何のためのものか**や，**どのような働きをしているのか**といったことが所見でなんとなく分かる名前を付けるべきです（束縛変数は除く）．そのための最も簡単で一般的な方法が**英単語をつなげること**で，その英単語のつなげ方に「〇〇ケース」という名前がついています．

## アッパーキャメルケース（UpperCamelCase）
「キャメル」とはラクダという意味で，ラクダのコブのように各単語の最初のアルファベットを大文字にし，それ以外を小文字にする方法です．

**パスカルケース（Pascal Case）**とも言い，主にクラスや構造体，インプリメンテーション使われることが多いです．

例
```Dart
// 連立方程式に関連したことをするクラス
class SimulateneousEquation {
  // いろいろな処理
}
```

## ローワーキャメルケース（lowerCamelCase）
先程のアッパーキャメルケースとは異なり，**最初の単語だけすべて小文字にします**．
ほかはアッパーキャメルケースと同じです．

単に**キャメルケース（Camel Case）**という場合はこちらを指します．

主に関数や変数に使用されます．

例
```Dart
// 行列の行数を取得する
int getNumOfRow(){
  // いろいろな処理
}
```

## スネークケース（snake_case）
単語はすべて小文字で，単語同士を**アンダースコア（_）**でつなぐ方式です．

アンダースコアは，一般的な日本語キーボードであればShiftキーを押しながら右Shiftの左のキーを押すことで入力できるはずです．

PythonやRustなど，かなり最近登場した言語で関数名や変数名などに使われています．

例
```Rust
// 配列の中身を出力する
fn print_array(array: &[isize; 64]) {
    // いろいろな処理
}
```

# Dartのコーディングルールについて
本題のコーディングルールです．ここで示すのは[Effective Dart: Style | Dart](https://dart.dev/guides/language/effective-dart/style)に掲載されている公式のコーディングルールです．

例はすべて公式から引用しています．

## アッパーキャメルケースを使用するもの
* クラス（`class`）
* 列挙型（`enum types`）
* 構造体（`typedef`）
* 拡張関数（`extensions`）

例：
```Dart
// クラス
class SliderMenu { ... }

class HttpRequest { ... }

// 構造体
typedef Predicate<T> = bool Function(T value);

// 拡張関数
extension MyFancyList<T> on List<T> { ... }

extension SmartIterable<T> on Iterable<T> { ... }
```

## スネークケースを使用するもの
* ライブラリ名
* パッケージ名
* ファイル名
* プレフィックス（ライブラリ名を省略するやつ）

例：
```Dart
// ライブラリ
library peg_parser.source_scanner;

// パッケージ
import 'dart:math';
import 'package:flutter/material.dart';

// ファイル名
import 'file_system.dart';
import 'slider_menu.dart';

// プレフィックス
import 'dart:math' as math
import 'package:anglar_components/anglar_components.dart' as anglar_components;
```

## ローワーキャメルケースを使用するもの
上に書いてないやつ
* 変数名
* 定数名
* 関数名

例：
```Dart
// 変数や定数の例
var count = 3;

const pi = 3.14159265358979;
const defaultTimeout = 1000;
final urlScheme = RegExp('^([a-z]+):');

// HttpRequest型の変数httpRequestを宣言している
HttpRequest httpReuquest;

// 関数の例
void align(bool clearItems) {
    // いろいろな処理
}
```

# 参考資料
[Effective Dart: Style | Dart](https://dart.dev/guides/language/effective-dart/style)