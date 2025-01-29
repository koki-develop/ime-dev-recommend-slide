---
theme: penguin
title: 自作 IME のすすめ
drawings:
  persist: false
mdc: true
overviewSnapshots: true

layout: intro
hideInToc: true
---

# {{ $slidev.configs.title }}

Classi エンジニア LT 会  
<small>2025.01.31</small>

---
layout: presenter
presenterImage: https://koki.me/profile.png
hideInToc: true
---

# 佐藤光輝 {.!mb-0}

Koki Sato {.!my-0}

<p class="!mt-1 text-gray-500">
<small>学習 PMF 部 / kobito チーム所属</small>
</p>

- 27 歳
- 平成 10 年 **1 月 31 日**生まれ
- 誕生日は **1 月 31 日**
- 生年月日は 1998 年 **1 月 31 日**

<div class="flex flex-col gap-2 mt-4">
<span>
<a href="https://github.com/koki-develop" target="_blank" rel="noopener">
  <carbon:logo-github /> koki-develop
</a>
</span>
<span>
<a href="https://x.com/koki_develop" target="_blank" rel="noopener">
  <carbon:logo-x /> koki_develop
</a>
</span>
</div>

---
class: flex flex-col items-center justify-center
---

# IME とは？

---

# IME とは？

[Input Method Editor API - W3C](https://www.w3.org/TR/ime-api/#background)

> An _IME_ (input-method editor) is an application that allows a standard keyboard (such as a US-101 keyboard) to be used to type characters and symbols that are not directly represented on the keyboard itself.

<br/>

機械翻訳 :

> IME (input-method editor) は、標準キーボード (US-101 キーボードなど) を使用して、キーボード自体に直接表示されていない文字や記号を入力できるようにするアプリケーション。

---

# IME とは？

[Input Method Editors (IME) - Microsoft Learn](https://learn.microsoft.com/en-us/windows/apps/design/input/input-method-editors)

> An Input Method Editor (IME) is a software component that enables a user to input text in a language that can't be represented easily on a standard QWERTY keyboard.

<br/>

機械翻訳 :

> Input Method Editor (IME) は、標準の QWERTY キーボードでは簡単に表現できない言語でテキストを入力できるようにするソフトウェアコンポーネントです。

---

# IME とは？

要するに

- キーボードで入力した文字列をいい感じに変換してくれるやつ
- IME がなければ我々はまともに日本語を入力することすら難しい

<p v-click class="!mt-12 !mb-0 text-center !text-2xl">
つまり
</p>

<p v-click class="!my-0 text-center font-bold !text-3xl">
我々は IME によって生かされている
</p>

---

# ちなみに

- 「**IME**」は元々 Windows で使用されていた**固有の用語**
  - 他のプラットフォームでは「**IM** (**Input Method**)」と呼ぶことが多い[^1]
  - この資料内ではこれらを総称して「IME」と記載することとする

[^1]: 参考 : 「[インプット メソッド エディタ - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%A4%E3%83%B3%E3%83%97%E3%83%83%E3%83%88_%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89_%E3%82%A8%E3%83%87%E3%82%A3%E3%82%BF)」

---
class: flex flex-col items-center justify-center
---

<h1 class="question" v-click="0">
Q.「IT エンジニアが使うべき IME は？」
</h1>

<div class="flex flex-col items-center">

<ol>
  <li class="option w-fit" v-click="2">標準 IME</li>
  <li class="option w-fit" v-click="2">Google 日本語入力</li>
  <li class="option w-fit" v-click="2">その他サードパーティ製 IME</li>
  <li class="option w-fit font-bold !text-4xl" v-click="3" v-mark="{ at: 3, type: 'underline', color: 'red' }">自作 IME</li>
</ol>

</div>

<style>
h1.question {
    @apply text-center absolute whitespace-nowrap transition-all duration-300;
}
h1.question.slidev-vclick-current {
    @apply top-1/3 left-1/2 -translate-y-1/2 -translate-x-1/2 text-4xl !mb-0;
}
h1.question.slidev-vclick-prior {
    @apply -top-1/4 left-1/2 -translate-y-1/2 -translate-x-1/2 text-2xl;
}
li.option.slidev-vclick-prior {
  @apply opacity-50;
}
</style>

---

# 自作 IME を使うメリット

- **欲しい機能を好きなだけ搭載**できる
- 何か不具合や不満があっても**自分ですぐに修正できる**
- **常に自分のために最適化された IME** を利用できる

---

<h1 class="!mb-0">IME 開発って難しそう？</h1>

<p class="!mt-1">
<small>※これ以降は Swift を用いた Mac 向け IME の開発を想定した話になります</small>
</p>

- ひらがな → 漢字への変換
- 辞書データの用意
- 変換学習
- etc.

どうやって実現すればいいの？

---
class: flex flex-col items-center justify-center
---

# AzookeyKanaKanjiConverter

---

<h1 class="!mb-2">AzookeyKanaKanjiConverter</h1>

<div class="flex items-center gap-2 !mb-6">
  <a class="!text-base" href="https://github.com/ensan-hcl/AzooKeyKanaKanjiConverter" target="_blank" rel="noopener">
    <carbon-logo-github />
    ensan-hcl/AzooKeyKanaKanjiConverter
  </a>
</div>

- ローマ字 → ひらがなへの変換
- ひらがな → 漢字への変換
- 日本語・英語の予測変換
- 変換学習
- ユーザー辞書
- ニューラルかな漢字変換システム「Zenzai」による漢字変換
- etc.

<p class="!text-3xl text-center font-bold !mt-8">
まさに日本語 IME 開発のためのオールインワンパッケージ
</p>

---

<h1 class="!mb-2">AzookeyKanaKanjiConverter</h1>

<div class="flex items-center gap-2 !mb-6">
  <a class="!text-base" href="https://github.com/ensan-hcl/AzooKeyKanaKanjiConverter" target="_blank" rel="noopener">
    <carbon-logo-github />
    ensan-hcl/AzooKeyKanaKanjiConverter
  </a>
</div>

```swift {*|1,2|4,5|7,8,10,11|13,14,16,17,18|*}{}
// デフォルト辞書つきの変換モジュールをインポート
import KanaKanjiConverterModuleWithDefaultDictionary

// 変換器を初期化
let converter = KanaKanjiConverter()

// 入力を初期化
var text = ComposingText()

// 変換したい文字を追加
text.insertAtCursorPosition("あいえむいーはせかいをすくう", inputStyle: .direct)

// オプションを指定して変換
let results = converter.requestCandidates(text, options: .withDefaultDictionary(/* ... */))

// `mainResults` には変換候補の一覧が入っている
print(results.mainResults.first!.text)
// => IMEは世界を救う
```

<div class="flex justify-end">
<a class="!text-base" href="https://github.com/ensan-hcl/AzooKeyKanaKanjiConverter#readme" target="_blank" rel="noopener">
  参考 : README.md
</a>
</div>

---

# Mac 向け IME 開発入門するときに参考にした資料

- [Miwa さんの Zenn 記事](https://zenn.dev/en3_hcl)
- [日本語入力を作るときに必要だった本 - BOOTH](https://booth.pm/ja/items/809262)

---

# 参考になりそうなプロジェクト

<h2 class="!mb-2"><a href="https://github.com/ensan-hcl/azooKey-Desktop" target="_blank" rel="noopener">ensan-hcl/azooKey-Desktop</a></h2>

- AzookeyKanaKanjiConverter の開発者である Miwa さんが作った IME
- 元々開発されていた iOS のキーボードアプリ「[azooKey](https://github.com/ensan-hcl/azooKey)」の Mac 版

<br/>

<h2 class="!mb-2"><a href="https://github.com/mzp/EmojiIM" target="_blank" rel="noopener">mzp/EmojiIM</a></h2>

- 絵文字入力の IME
- 「[日本語入力を作るときに必要だった本](https://booth.pm/ja/items/809262)」の題材

---

# 参考になりそうなプロジェクト

<h2 class="!mb-2"><a href="https://github.com/koki-develop/Koto" target="_blank" rel="noopener">koki-develop/Koto</a></h2>

- koki が普段メインで使用している日本語 IME
- 内部的に AzookeyKanaKanjiConverter を使用している

<br/>

<h2 class="!mb-2"><a href="https://github.com/koki-develop/NyaIME" target="_blank" rel="noopener">koki-develop/NyaIME</a></h2>

- 猫のための IME
- [InputController.swift](https://github.com/koki-develop/NyaIME/blob/main/NyaIME/Sources/NyaIMEInputController.swift) を見ると Mac 向け IME 開発の雰囲気がわかるかも

---

# まとめ

- IME 作りましょう
- 日頃からお世話になっている IME に感謝の気持ちを伝えましょう

---

# おまけ

- この発表資料は [Slidev](https://sli.dev/) で作成して GitHub Pages でホスティングしています
- ソースコードは [koki-develop/ime-dev-recommend-slide](https://github.com/koki-develop/ime-dev-recommend-slide) で公開しています

---
layout: new-section
hideInToc: true
---

# ご清聴ありがとうございました

