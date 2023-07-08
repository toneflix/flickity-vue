# Flickity for Vue.js 3

[![npm](https://img.shields.io/npm/v/@toneflix-code/flickity-vue.svg?style=flat-square)](https://www.npmjs.com/package/@toneflix-code/flickity-vue)
[![npm](https://img.shields.io/npm/dt/@toneflix-code/flickity-vue.svg?style=flat-square)](https://www.npmjs.com/package/@toneflix-code/flickity-vue)

A Vue 3 Component for Flickity.js - See a live demo [here](https://code.toneflix.com.ng/shared/flickity).

<p align="center">
    <img width="200" src="https://flickity.metafizzy.co/img/flickity-illustration.png" alt="Flickity">
    <img width="200" src="https://vuejs.org/images/logo.png" alt="Vue.js">
</p>

## Vue support

Supports only Vue >= 3

## Installation and usage

See official documentation [here](http://flickity.metafizzy.co/).

$ npm i @toneflix-code/flickity-vue

```js
import { createApp } from "vue";
import App from "./App.vue";

import flickity from "@toneflix-code/flickity-vue";

createApp(App).use(flickity).mount("#app");

new Vue({
  components: {
    FlickityMain,
    FlickityCell,
  },

  data() {
    return {
      flickityOptions: {
        initialIndex: 3,
        prevNextButtons: false,
        pageDots: false,
        wrapAround: true,

        // any options from Flickity can be used
      },
    };
  },
});
```

```html
<flickity ref="flickity" :options="flickityOptions">
  <flickity-cell>1</flickity-cell>
  <flickity-cell>2</flickity-cell>
  <flickity-cell>3</flickity-cell>
  <flickity-cell>4</flickity-cell>
  <flickity-cell>5</flickity-cell>
</flickity>

<!-- if you don't want to use the buttons Flickity provides -->
<button @click="$refs.flickity.previous()">Custom Previous Button</button>
<button @click="$refs.flickity.next()">Custom Next Button</button>
```

### Configuring with props

Any options from Flickity can be passed a props

```html
<flickity
  ref="flickity"
  prev-next-buttons
  page-dots
  wrap-around
  :initial-index="3"
>
  <flickity-cell>1</flickity-cell>
  <flickity-cell>2</flickity-cell>
  <flickity-cell>3</flickity-cell>
  <flickity-cell>4</flickity-cell>
  <flickity-cell>5</flickity-cell>
</flickity>
```
