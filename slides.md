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

# IME とは？

- Input Method Editor (Input Method)
- TODO: IME についての説明
- IME がなければ Hello World プログラムを書くことさえ難しい
- 我々 IT エンジニアは IME によって生かされている

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

- 欲しい機能を思うがままに実装できる
- 何か不具合や不満があってもすぐに修正できる
- Zero Configuration で常に自分に最適化された IME を使用できる

---

# IME 開発って難しそう？

TODO

- ひらがな → 漢字への変換
- 辞書データの用意
- 変換学習
- etc.
- これ以降は Mac 向け IME の開発を想定した話

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

---

# AzookeyKanaKanjiConverter

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
class: flex flex-col items-center justify-center
---

# 簡単！

---

# IME 開発入門するときに参考にした資料

- [日本語入力を作るときに必要だった本 - BOOTH](https://booth.pm/ja/items/809262)
- [Miwa さんの Zenn 記事](https://zenn.dev/en3_hcl)

---

# 参考になりそうなプロジェクト

- Azookey Desktop - (Swift) https://github.com/ensan-hcl/azooKey-Desktop
- EmojiIM - (Swift) https://github.com/mzp/EmojiIM
- Koto - (Swift) https://github.com/koki-develop/Koto
- NyaIME - (Swift) https://github.com/koki-develop/NyaIME
- TypoIME - (Rust) https://github.com/toshi-pono/TypoIME
- GyaimMotion - (Ruby) https://github.com/masui/GyaimMotion

---

# まとめ

- IME は与えられるものではなく、自ら作るものである

---

# おまけ

TODO

- スライドの URL / GitHub リポジトリ
- Slidev の紹介

---
layout: new-section
hideInToc: true
---

# ご清聴ありがとうございました
