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
class: flex flex-col items-center
---

<Header :page="$page" />

# Q.「IT エンジニアが使うべき IME は？」

---
class: mt-24
---

Q.「IT エンジニアが使うべき IME は？」 {.text-center.font-bold}

<div class="flex flex-col items-center">

<ol>
  <li class="w-fit" v-click="1" v-mark="{ at: 4, type: 'strike-through' }">標準 IME</li>
  <li class="w-fit" v-click="2" v-mark="{ at: 4, type: 'strike-through' }">Google 日本語入力</li>
  <li class="w-fit" v-click="3" v-mark="{ at: 4, type: 'strike-through' }">その他サードパーティ製 IME</li>
  <li class="w-fit font-bold !text-4xl" v-click="4" v-mark="{ at: 4, type: 'underline', color: 'red' }">自作 IME</li>
</ol>

</div>

---
layout: new-section
hideInToc: true
---

# ご清聴ありがとうございました
