---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# TypeScript 的具体应用

Presentation slides for developers

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# 序言
TypeScript（简称 TS）是 JavaScript 的一个超集，提供了可选的静态类型检查功能。它由微软开发，目的是在 JavaScript 基础上添加类型系统，使得开发者在编写代码时能更容易发现错误，从而提高代码质量和开发效率。TypeScript 会在编译时检查代码中的类型错误，并将代码转换成纯 JavaScript 代码。

- **图灵完备** - Typescript 是具备图灵完备的编程语言，而不仅仅是 js 的超集
- **类型系统** - 支持静态类型，可以显式声明变量、函数参数和返回值的类型。类型系统帮助开发者在编译阶段捕获错误，提升代码的可维护性和可读性。
- **编译过程** - 需要编译成 JavaScript 才能运行。TypeScript 编译器（tsc）将 TS 文件转换为有效的 JavaScript 代码。
- **开发工具支持** - 由于类型信息，现代 IDE 和编辑器（如 Visual Studio Code）能提供更强大的代码补全、自动提示、类型检查等功能。
- **接口和类型声明** - 允许使用接口（interface）和类型别名（type）定义数据结构和函数签名。这使得代码结构更加清晰，并且更容易进行协作开发。
<br>
<br>


<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
transition: fade-out
---

# 主题

从具体应用的角度，用以下几个主题做简要介绍

- 🎨 **不止 any** - 泛型，条件判断，遍历，约束，编辑器提示，never
- 🤹 **应用技巧和事例** - 链式推导，递归求解，字符串匹配，遍历取值，
- 📝 **主流开源库** - 类型定义，导入导出，文件排列
- 🎥 **当前项目** - 类型定义，编写成本，收益
- 🧑 **高阶概念** - 交并集，逆变和协变
<br>
<br>

参考资料 [TS 官网](https://www.typescriptlang.org/) -- [类型体操](https://github.com/type-challenges/type-challenges) --[高阶应用](https://www.zhihu.com/column/c_206498766) 

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
---

# 名称解释


|     |     |
| --- | --- |
| <kbd>泛型</kbd>/ <kbd>Generics</kbd> | 它允许你在定义函数、类、接口或类型时，不预先指定具体的类型，而是将类型参数化，直到使用时才确定类型。 |
| <kbd>条件判断</kbd>  / <kbd>Type Guards</kbd> | 条件判断不仅限于简单的值检查，还可以基于类型执行类型保护（Type Guard）。通过使用条件语句，TypeScript 可以智能地推断类型 |
| <kbd>逆变和协变</kbd>/ <kbd>contravariance/covariance</kbd> | 类型兼容性和赋值 |

---


# 基本示例
- **泛型** - demo 项目 充值中心
- **条件判断** - 通过类型定义进行约束 [demo](https://www.typescriptlang.org/play/?#code/GYVwdgxgLglg9mABABwE4zFAMgUzAcygAsAKANwEMAbEHALkQGcp0DEAfRMEAWwCMcqAJSIA3gChEiGMEQkoAT2Q44syjRyIAvDsQByZq3x6REqVIgJGcKjgB0VOPnLVaDvISJCA3FID0fogABuq0QYiA1RGAFcaAtaaAXHLBhhj4QZKIAL6IOFSMmmbmlmDWtg5OLhp2UHAAYjAAHjgAJiQATEI+-oEhrjjh0fHB3PyCqVLp4uPiaBjYHsQkAEQAEtmOADSIAOpwqFSNAIQLPlOsswTzACxt3uK3EFQUjIyIACJOYml8FKgA1iSmaQsVhs9kczgW21Uh2OYwmdweT0QAGEKFAPlIeCoAO7-dEFYElMGLACy2OhN1hk1AkFgCEQPAoPxwAGU4OBmhQwDAGVQGG98BxkaiAVIZHJOdzqNIilBORAVLJ+SLzBKeXYvr9-r5EAFgqrqH1YgkgvzRhksjk8oDEPqqHZMXAcR0dV1bYaBkEUVAzeNJoVmIhGu8tFwcFjXmVjgymaz2SQg-hjuJ-WiIKjtKHw16teJoyy2WBmmmoMcgA)
- **收窄类型和穷举检查** - 穷举和never [demo](https://www.typescriptlang.org/play/?#code/JYOwLgpgTgZghgYwgAgGIHt3IN4ChnJgCeADhAFzIDkMmVuAvrrqJLIigEJxQ76GkK1AEY96TXMTLIAggBs5yALxpMyAD7JuUZrhgBXEAjDB0IZAAs4IACZyIANThz9EABQA3Z5XlyAlHwEAM4A7sBgCBbIns4AdFIQAXgEBAhwQSg0dOT8KcgA9PnIgJvxgDOJyF6KgNURgGymgCFegFxyqui5KcJQEHAA1q1pGSJiOXkEhRXOyIAU6mWA9GZaPK0E7Z09eTYQ8PpyYEPDo5WTM8ggEB7QC8gIZkFgyBAAHlb618CnAMIWEAhdlMenvCqVc5Lbr8JgMIA)
- **继承和约束** - 链式推导[demo](https://www.typescriptlang.org/play/?#code/PQKgUABBCMBMEFoIGEAWBDAlgO3QIwBsBTCAeQAcAXTAe2wGdJEEXWm8BPCAQW0tTpcAYgFcIACgAC6PgDMRASggBiALZEAJphGqV6cuQKYAxump0wTZdYgBFEUXrnslqGiy5CJGlVoMI6ABOJMY0qqp0BFwi9JoQOBAAUugAbuj0xoGYVAB0EABCIpQQAO6oRNilJPQlmJTGqBCUNBAAKhzkRADKmdmUADQQppUcNGLkgT5EgVFNHSR1APyuEACSlfyY9EMYBMTYAOZEg6Ni2ERxzXOdAZU0eABWRMbFNIEBQwTp20hlZkQpaYQU4QIwAaxISCuExoKUwGhIlBKLXk2BefggAAMfM5xBCOIM0gQHApMbcNFijpRxKS8ussTi-JiTmMhjIIEQAB6UCoU-ghESBYJ8IZ0WSYA7XEicJrlCAHTCAyr48kQIkOPIAdWqAhEBAp+DGxSu6GMxkc235EHFuAIEGC9D1xTh6EpREomJyKyEbw5nPQqkMRBWmNDlEYUARxi+wVFDGKoWw4oOAC4UBgcPhiCtE057Y4nRAALxx5NMKA5Rl0cQAclkNBoNcGcAAzApyxBK75qzXcOomxAa5R5ggGug9hUjvQa+2oBWq9ha3gggOAN5q8cONM1gASRD2LU1b31NYgAF9Z3OclSaStgMA-Z0XrLEfMIDRZPnHQRjS08EQUyYHAeUCWRTRIAAlAsfwgVcO3rGg02wHR-0CDs+wAiAnCyQ4O2XQI0zguc53VTDsJwA4OzPJhqKgUNMRWABNVkNDoIcIHOS4WhKLIeVuLgHnoYBw1BGgFWMJoWgwbANGIF8IBhLxdCQB4YmKBJhxuYhAQIL0mGYsRhgCehHXUWUzCxfEyUiLhTXNKhtkxcjDjJGQ+TlTFSLJIz-34zZDkQCBVLzYhUgWYp0gQLY8i6AMSExKzSjY4pfPIb5Llqc09KgAA+CAADVMCIEp30qABxOodxEPA01QShKHIegU3vcMGhyQTK0CA5gDgMAQGASxQAgAB9UaxvGsaIAM95kBoBEID3WMJuW0aIH6yxNJIdxMy8AAeVpi1gs88pLIj327bA012gBpP0eRk7ZnIOQZ8py8QO3xNNbq5e6NG2fEPzaCBFg4gEgS+-oO1ItN8svIs8u+7leX+ohRk-A6Qe2zxiF20hVDqfbBmuvKADIICg0JAg0G6XpyvK0yxrMiH2iAyYpt5qeu2mcqYKk0xpYs8taMBqLAIaVuWtpHGKZB0kcEaJfGtaBswQM3mNN9124cFjggABRTkn2KM9rUmXQa0kTbR12fYp2AIpMAIadLCjGMQjoPN0AZjNseDMBc2KB0nWgQ70CYLtcTrBsB1bS8I78JcV0GddocHPcDwgI8Zg0U8L3DhdawwgchxHMcJ0ORwZ3Dm9239j3A+gyh4BLMP5wuwu4uLmQaH5d4i8ve8IEt+gEC5I3R6FN58-b3tO8GGsvjzfvq-dW86-jL8nRbUPp8jov5+73uOM7geH2H0fDeeSgJ8mNC273ueYFgNsV+pWvNrZWJthLABtJgDaNrtbWmAIS7U2oDIOP5oCDAAVfTQ0A6aQygLAl4QCdZgPmBAxusAYGXxeJoWAiD-54MoGgkBzNwGfkgZQFsuCjaaBbEQgAuhtN8KCeQaBDqdJgCEkIoWmOwIIhEoabjIpQHClEoC0WPuoNMT0RasJuOwghh0zoYTkeIiiCiwAf2URobe3CoDqI4vwtCotxaK0mqIQIR8ug8kagrSxw1lZi3ALlCAXQMCxlOO8egNBiTOCahAOqDUmotQyKgdq9BOrdTgMAGQNQBHuMKsVLC-iHYe1qvVRqzVhIRKiTEnqsBgB+ICX4CMEA8oAFk3hbRtpORwWTQm5NapEjqbxKLrSAA)，递归求解[demo](https://www.typescriptlang.org/play/?#code/PQKgUABBAsCsCcEC0EBiAbAhgF2wUwDtJklSziAjATwgC8ALAewFcqBLAWzYIHMIAKAAIBjehQBOjAJQQAxBzwATNsw5zM48Ziphis-RACKzPAGdsbRkWIBJAhGz02piKMzp0hHngA0EKiwQAO4s6IoQBHhKDozB4mz4EJgOVAAOeA70OA6YANZmSfYaWjSYBOF4XLjRjhkAZljVRZraKekAdLpQqIziEHgAHpgcqZ4AXF0QAAYz2KbE2Gn1jfj2ALxoK4QAPADaAIx+AEx+uwDMftAAuqe7u7BXj1cAfBDAwBAHx34XMH4PxBmU0mrwAamw8EEIFYIABxBIACWYFDGEHouFSpjG7zmonaACtTO1ejxgHB4GAQMBdKAIAB9BmMpmMiAATRYfQAwoxFBkEXhxBlmcKGRAqbpFulNjhVtsACr9AarRQuZgEXIERhBAi7F4QDYKwbKly7bh1AVoPzta1mi0AGSuxAA-GhFcaIGqNVqdY6oFAXbtre0MDKdqhnlbrSGmts7c9fX7UbtUJHg1sCLH48RUXKANw0kD0kXMiByszYCCczCmArFkvizipXoVyUZADeEAAogBHZjuPydgbpYQVgC+EDqkjUAHJBK2kG4PF4zMBmBZ0KZpxKlq5qwUNrtiIPh9htj2++httHZbqI58XhGj0O8COz733Ff03tDhAThBftcd5fL+PyXA+PhPieb4Xp+oYZsBuxHI8QE-khzyPlAx4vqe54fteOzAX+5xgbc9xPC8pyoaBfwQA86EQZhz6vrhl74fBHZ1IwjCotOFAaNOxyovsAAMECjn406cYwfHiNOFGfBxXE8TJAm-kJoniRAklcSp4FgI6YDvBAc6mEggwnmZmi9GArb9FZfQbGx2zTvs07PAWRZ1qKqDMOItR9AAyvgmKeV5YrUqAxCvAFWSCv4HIQKYjDoGulgEFiaIYliOKmHihLEuIpLksAZSmEEApRRA4KQolyWpVYGXotgmLYsAuL0ASRIkmSCDAElKUWA1lUALK9BknJZEuvBmKiTUtTleVdYVlLUkAA)，字符串匹配[demo](https://www.typescriptlang.org/play/?#code/PQKgUABBBMAMDssIFoIBEBOB7ADhAwgBYCGGkKylV5ARgJ4HE4AuxAlgHYDyAZgAqEAQhAAUAAXxNWnXgMEBKCAGIAtgFMAJmwCuK5czUqcAG2IHkxtgYzFjyzjzVlyS1xACK2tQGdmbLBxg5Ji4EMQQ3jhqAMZsPGyaENEkGBA82HrhvhicAOYAdEFQAGJYqWoAHsRGxmoAXEUQAAYtzN7kzHRREILazNY8xgwAvOjYOESkADwA5BA0ENoQzMsQahCpPBB2DACEEDMANAcHAHwQwMAHNH0DQ7sz5C1NjecAagkA7hABEADiVgAEtoaHUIIR+jhvHVLm1kvkAFbefJlXLAOCIMAgYBBUAQAD6hKJxKJEAAmlhtKl8FgNOtAU51iTmYSINigp1uiEJikpgBlNYVAwcDTeCLMHIcXLHfCC4Wi8WS3LnYbkAWVeVipoAEgA3g4nBAcBg1PEKgBfPX4S36jiOVLebQ8M3ml5QKAAfjGuEmGCmOt1xtNbAtesdzpDrplp3IUDBfIA3LiQASWSSIAAVHwrSTeHyptOk9lsIxlFac9a6iAAUQAjtpbMdqxUotEVua0hkDmIK8hkrZalKfMA+mxjN5HmAK0liHmxaMANrkS4QHveZCVVvMDcYbBkKDNrdTOsN4xTbm+2Y3fqGwZ0B7HGYzU6P693e-Pl-kQ8xZjH+u2Oe4yXjMb63vcRwnM+r63E4d4PKcX4Hi2v7-qeQE+ryoGwZsEGPghME3rhdCfoc34oW2aGAReWHuvMOFpPcdF0ZBczQdcOHwaR5FHie1HAbRCxLOWawbGk2wQHsByPmchHvghSE1hRf58WeNHTHMQmrCs6ybBJUmsTQ7FzIs2miXpOwQPs3HIbxAFqQJGnzKZIm6eJlnWY+zDGc5SxQG5WweWcX4ALrJgWhb4hAxRUswhCGnyBhQhFhZsjioDkOcfIpOsdCUg6WDGKOATQuCkLQrC3jwkiKIYGiGKwMAxAcN4nxOJlEAfGo3zeIVxUtWCELMFCMLAHChCIsiqLoggjW9UVfglR1ACyZTrJMxiDrkPiDeVo3jZNtW5FiOJAA)，遍历取值，
- **逆变协变** - [demo](https://www.typescriptlang.org/play/?#code/JYOwLgpgTgZghgYwgAgIImAWzgG2QbwChlk4BzCALmRAFdMAjaQgX0MNElkRQBEB7MsggAPSCAAmAZzQZseIiQZwoAawAUASmoA3fsAmt2hHBDCk5uauiy5kAXgKkK1AIwAmZCwDc7U+YlBagEhR0VnKmQPABpiZGU1ai0HAD4COLYfYyA)


::right::

<Toc v-click minDepth="1" maxDepth="2"></Toc>

---

# 主流开源库

用贴近我们日常使用习惯的 antd-table 组件为例子，它的上游库是 [rc-table](https://github.com/react-component/table)


---

# 当前项目

tool-mod mod二期

client-charge 充值中心

act-temple 活动模板

activies-customized 活动组件库

收益和成本


---

# 能力边界

runtime 和 compiler

高阶：[JSON parser](https://www.typescriptlang.org/play/?#code/PQKgUABBBsBMsA4IFoICkDKB5AchACgIYBOAzgKbGQrK13UBGAnhABJMAmxA9gObkA7CAAoAAgAsmPfgEoIAYnIAPAC7FyAW3IKVmgA4AbQruQGAlruKEDCgFaluAsNXmuIARQCu5UirOPnKABNbk8AcnUIdQBHTzN1DggVbggzDUNNQRUIQiSmPXJTcgA3chs9EhUDFgqySiSU2op0bDxfYjMBXlSBZJyIbgZbcgBjbPNLazyCgDpAiAAlclj4zN7SAC5qFAgAAxxPDQZKUl2cgUTdgFUBMxHuDm0fEcICkQAdTyVvpRkzzpauAgLyEx1SvAE3ASMwgIU8EAE5HIHAEYWyfSa2hU4k0c2oAD4IAA1MzkADuAyEAHELKxPAwNhBxCoVHpNsBgCpSCNxDN7DMobxgHBEGAQMBnKAIAB9WVy+Vy2GhYgQADCD20rEo2gVutlEHFkuAECYyvOpDJJzAKny2nwnnUAB4ACqEgC8EAA3tQANr4HoQADW5FNADMIM6ALqM51+yMQZS6C6kAZDUbZAD8BAd5BdccJMbjAG4wABfEvW20QDDkFT4HgFYg2l0AGggAGkE6pBBwU-XuI2be2Q22ie6vb7-QDg2GIxAAD4d6MELtJ3sdiBZokQRn+xM9lMz7jh52biNxncIkqUEvl5w2t7O7jBoQesKesILiBhUufxdhH0-2-SMgLCDZQJbIDdgAIgAEk9dpOl4UtoLORd6zSCwzFKCsHztDoNCw0oIA9ARPAMGxFzUbwv1DawKFwqsDiOShnSrN1qEXXYAAZdk4vYAEY+KgLjYGEr9dgAZnEriABYZL2ABWBTdmgFSAHYVIQFSAE4VOQXYK3vKsiDqF1VwPCBEK6cd7SdUyKAAGQsShrBdZ9BDMAAvXNXXxH1uMjfFGMfDzbh8x1qAwFtqFPfdkwjMKfXjD1krAccMAshLdngzpQ3qAAxeJfFLXKBHylUlhK8SsyKshsni9d31A38vwA0CQLa8C2sg7YzyfF9vNzKqVDbH0Zgm502zq3wgr6xkZoa7tstQvqswc8gMDUJCqvIlRHRGwlGpTH0+qgKA8vqEaYvO26egqxKXyy9cYPg6zkNWu6IEjM7+rCoaDp8UaIHGya2wGwQ5q+xlEVKKhboW4qlrXFNdhUNC9lDDHdgEcSoHWkgKAwwi-FKXaDH2jAjuW9dTq+i7yquoGbvpy6VQhoRjr2OCEO2roUIxsiKK-ajtEXOiDAoX6fq+rMOYB66QYmmYpseyH8V+mHr3h87Efq56U2Y45iDYgo1qvOH5ogRaDb2O2uPedGJPeXHzfliLFddK3YcoagYyMvCCEJ8hnMmAxzK5jnkvHOKaZO6hXt5jp+dQr8hcopJiBo8X6PIMAZbPP1g9D1yDHJ-bY0C-EC93YPy5dYLjLeDb69jlG1YEaOSLnLm6fuwqkY5lnlbZxYgY5lNI6Sn6C9qwewtt5rzY2rA0zGeuRonjWEet+enq59rl+DgBBYgrCYDfx7C0ht91i3fagLW4ZCu0T7PwgL58PbIqgNvLKjyMLNy6208AIQMkIySdxSiDH6MdbY+lHotNsI9GaVSvvvOOHdkqz13vrA+IFzY+nLm2TeYUC6P1wb4RevVboEzqKfc+l9fBDzHqQPat8KFEmsN4Bu8DR7FG4eQNs-DSEYPbgA8hZ4NoMI-vXYoojBBjWVsQiAAiDDeChnfH2Osn43ibq-Ooq9hjry-hTCOmCAEkNMdkD0npSxwN7tQRBSNh4TVHiNW2AD87UDnngzBP4wiEJUSNSResqEHxoedOhFAjHpiYcDcuHDLw2y5rsd4PNR4GGUJkUs6S8ZSMIPEQGvgrFsIpm2LJShMjU3bn3L6o98DEN+gzB6CjOYWOntLX60TyCxJMWU-abS2yNOsUkih2jvbaz9vfYgL8g5FOoB4qeL5kpAOsd3OxLNhwsC5u9buYRAnjiWZghBqDKHAxQa09BghPHTxwSk-x4FzZcPUcNa5AgamWVOQ9NR3hhFnLaZI-GIMax1gbJQZsKjtltl+eQfEpSVAcyBZeCZO9UWXiIdYhFkY5kvJ4cc8R08jlA3gU4s5SDqCXKZswheyzBBpXuUjW2aSMlnNhbkz6USQawoRUiq2Dz25L1oUHQxa8VDxI5p8hK3z6hEhUaPOVQNkVZh9IqgZo4QmaxmfyplB9AJH3oe-T+AzimIrClK2mCr5VnLVSoZVIM1V7Q1UqrV6KKECsssTIiedhU+iQaws1L5QnavGdrOZG0S5WDLtY8x7dE7vQFmnciGdRa0Vzu6WKzLWUPS2snXg6pehZETVmG4zxXibT5rwR0uakIFqTCoAsEY5mlu5OWmtXRq223ehmqAmVUllQeotUqnpR41nuBcYd7igalnyVmHKnoh3wTHY4DgM7mXvBdvk4FaSBDwRbS8Ao7aq2HRnVq+di7PTLonWcVJG7iBbrPGk4ge7EStsPZW01+JT3Qz2PBC9V7V03swWk94WNul7FAy+st7682fu-XdRk56kbDoA2u297wGAPrnRhqDb6K2wZPQ+xDf7kNLtGCutDwGN3o3A2klQuGD34aQnBojv6F2kcveRidDG20fsI1bDAcyACieHVTiBIIQMYUJO27MrRlZlrtt2bumX24D96fEQfUxQ1TcawNKb05eHTlldiYY02k0z2nmU0aU9Zwz4bg5HvrlFLtla1kDJc3m7uuw+LyfQwOge9VJ0AunTVEVFBHMxsVvO8uw6ROMbExJqTxBHSLS-bsW+jIjMrX82g6qGnMUlO5vBGLqEa7VnXbupOSF4NZnRZl5lOXzlBauXl4FG0Ismqi8V6xw6h3pemdo+zdQvWk3IPXLL65u3dwm6jUWjWRo1ZBorUWZWZuY1zvNkL+XFYSwoKthTybNutcLordOZXBuShADKPUCoIwktVIQCgKYbu3cNGkPQUJ0RVk9BAITsRrBtiE0oAoYwIClggKGHgGhvyiDwsgHk1gsldB8MATwfhJaBMrG8XQVDu7nQ2o6B93p6YQGgoQaCjJoIMGgm2ZppPqeMl20IiAdPoIjApyDUWbYmdtmgjiCi3AacThJ1AMnHOqdC7p6LhnEPc509LIAlnJPoK3AMBz9Ov1Sx9X61j7QLwnvdz7kDkH+0-ueDcsIPqBOies-J5T6ntPlcy550r+mbOOc+i57LyWzO+dlAMILtsxORdi-t5LkX9OOdM-l4r1nqv1fJs19r2+Mg2yW9usH26quYaJ6+iMRknus7M5d2EfnAewhB7p4QRkYQGCBJJwyb3UsvoK9+o36PX1q-fjr31LX1AZD4nhdQY36ZHRm7cgT98v54VensUP4fwPR-j-DpP5KYQZ-R3n1AEfYwx--ZX8HR0AEBIgRn9owfMUF8m73+bg-Zk0RF-X22UWF-5g79N-vn+YXcwAWglqAXQuXuLuZ2T+voYQ-+5ez+Re3OucbYZ2BIW+v2i+u+y+X+6e+Oh+NuyuZe3Ad6G6AgG6DAG6oY4uZIUIBgHA0Emu-WUAqeIgfUme50pe-uuBxALsGGoGYE34ZBxAFB9e50WutBCBl+2+yBH+t+jok+P2AklOPBFB0EYOT+Myr+V+S+n+1uP2fuAu1A1AchlBjIAksAkkYO6WcB2sr+P0YAUoL28o1sDo2I9QW05AbI12Nh0oBoEooABI1Y4mkQpoDoVk3A6ifgjgmwTILIbIGwHIXIPIfIpAAoxAQoIoCAwAhAAgFoD8EAhIJI5IgRwR-g6RjIzIrI7InI3IvI-Igowo8AKRDg+RoR3hAAslCNoAlhRIIPwGEcUZEdEeUXEQkbwGKBKEAA)

[lisp complier](https://zhuanlan.zhihu.com/p/427309936)

会编译原理就是可以为所欲为 [craftinginterpreters](https://craftinginterpreters.com/)
<!--
Notes can also sync with clicks

[click] This will be highlighted after the first click

[click] Highlighted with `count = ref(0)`

[click:3] Last click (skip two clicks)
-->




