# Vue

大多參考官方建議

## Common

1. 結尾 `;` 勿省略

## Instance options

1. `data` 需是回傳 object 的 function，除了 `new Vue()` 內可以直接是 object
1. `props` 的內容越詳細越好
1. private property 使用 `$_` 開頭
1. `computed` 內容以單一目的為主
1. options 之間無須留一行空行

### props

1. 定義時命名使用 camelCase
1. 在 templates and JSX 內使用時用 kebab-case
    - `userName` -> `user-name`

## Component

1. 單個檔案內僅裝一個 component
1. 檔案命名使用 PascalCase
1. 名稱勿使用省略的單字，例如 Button 使用 Btn

### 命名規則

1. 名稱使用 PascalCase
1. 基本元件使用 `Base` 開頭，例如按鈕 `BaseButton.vue`
1. 單頁面只使用一次的元件用 `The` 開頭，例如 header `TheHeader.vue`
1. 元件間有上下層關係，下層元件應用上層元件的名稱當開頭
    - 主元件 `List.vue`
    - 子元件 `ListItem.vue`
1. 單獨頁面元件使用 `Page` 開頭，例如 `PageLogin.vue`
1. 使用較常見的單字當開頭，形容詞或動詞結尾。套用官方的範例如下
    - `ClearSearchButton.vue` -> `SearchButtonClear.vue`
    - `RunSearchButton.vue` -> `SearchButtonRun.vue`

### 使用規則

1. 沒有內容的 component
    - 在 single-file components、string templates 和 JSX 內無須成對，只需 `<MyComponent/>`
    - 在 DOM templates 內請成對 `<my-component></my-component>`
1. 在 single-file components and string templates 內使用 PascalCase，但在 DOM template 使用 kebab-case
1. template syntax 使用簡單/單純的內容，複雜的請移動到 `computed` 內

### Element order

1. `<template>...</template>`
1. `<script>...</script>`
1. `<style>...</style>`

因 `<style>` 可有可無故排後面

## Directives

要麼用縮寫，要麼都不用

- `v-bind:` -> `:`
- `v-on:` -> `@`
- `v-slot:` -> `#`

## 其他注意事項

1. `v-for` 務必加上 `:key`
1. `v-if + v-else` 也請加上 `:key`，內容為自定義字串
1. 非不得已不使用 `<style scoped>`
    - 若使用，請使用 `.class` 或 `#id`，勿直接選擇 tag name 進行設定
