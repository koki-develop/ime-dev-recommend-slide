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

2024.01.31

---
layout: presenter
presenterImage: https://koki.me/profile.png
hideInToc: true
---

# 佐藤光輝 {.!mb-0}

Koki Sato {.!mt-2}

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

TODO

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

hogefuga

---
layout: new-section
hideInToc: true
---

# ご清聴ありがとうございました
