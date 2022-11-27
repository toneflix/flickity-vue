<template><div><h1 id="flickity-for-vue-js-3" tabindex="-1"><a class="header-anchor" href="#flickity-for-vue-js-3" aria-hidden="true">#</a> Flickity for Vue.js 3</h1>
<p><a href="https://www.npmjs.com/package/@toneflix-code/flickity-vue" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/npm/v/@toneflix-code/flickity-vue.svg?style=flat-square" alt="npm"><ExternalLinkIcon/></a>
<a href="https://www.npmjs.com/package/@toneflix-code/flickity-vue" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/npm/dt/@toneflix-code/flickity-vue.svg?style=flat-square" alt="npm"><ExternalLinkIcon/></a>
<a href="https://www.npmjs.com/package/vue-flickity" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/travis/drewjbartlett/vue-flickity.svg?branch=master&amp;style=flat-square" alt="npm"><ExternalLinkIcon/></a></p>
<p>A Vue 3 Component for Flickity.js - See a live demo <a href="https://code.toneflix.com.ng/shared/flickity" target="_blank" rel="noopener noreferrer">here<ExternalLinkIcon/></a>.</p>
<p align="center">
    <img width="200" src="https://flickity.metafizzy.co/img/flickity-illustration.png" alt="Flickity">
    <img width="200" src="https://vuejs.org/images/logo.png" alt="Vue.js">
</p>
<h2 id="vue-support" tabindex="-1"><a class="header-anchor" href="#vue-support" aria-hidden="true">#</a> Vue support</h2>
<p>Supports only Vue &gt;= 3</p>
<h2 id="installation-and-usage" tabindex="-1"><a class="header-anchor" href="#installation-and-usage" aria-hidden="true">#</a> Installation and usage</h2>
<p>See official documentation <a href="http://flickity.metafizzy.co/" target="_blank" rel="noopener noreferrer">here<ExternalLinkIcon/></a>.</p>
<p>$ npm i @toneflix-code/flickity-vue</p>
<div class="language-javascript line-numbers-mode" data-ext="js"><pre v-pre class="language-javascript"><code><span class="token keyword">import</span> <span class="token punctuation">{</span> createApp <span class="token punctuation">}</span> <span class="token keyword">from</span> <span class="token string">"vue"</span><span class="token punctuation">;</span>
<span class="token keyword">import</span> App <span class="token keyword">from</span> <span class="token string">"./App.vue"</span><span class="token punctuation">;</span>

<span class="token keyword">import</span> flickity <span class="token keyword">from</span> <span class="token string">"@toneflix-code/flickity-vue"</span><span class="token punctuation">;</span>

<span class="token function">createApp</span><span class="token punctuation">(</span>App<span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">use</span><span class="token punctuation">(</span>flickity<span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">mount</span><span class="token punctuation">(</span><span class="token string">"#app"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token keyword">new</span> <span class="token class-name">Vue</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  <span class="token literal-property property">components</span><span class="token operator">:</span> <span class="token punctuation">{</span>
    FlickityMain<span class="token punctuation">,</span>
    FlickityCell<span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>

  <span class="token function">data</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">{</span>
      <span class="token literal-property property">flickityOptions</span><span class="token operator">:</span> <span class="token punctuation">{</span>
        <span class="token literal-property property">initialIndex</span><span class="token operator">:</span> <span class="token number">3</span><span class="token punctuation">,</span>
        <span class="token literal-property property">prevNextButtons</span><span class="token operator">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span>
        <span class="token literal-property property">pageDots</span><span class="token operator">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span>
        <span class="token literal-property property">wrapAround</span><span class="token operator">:</span> <span class="token boolean">true</span><span class="token punctuation">,</span>

        <span class="token comment">// any options from Flickity can be used</span>
      <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token punctuation">}</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div></div></div><div class="language-html line-numbers-mode" data-ext="html"><pre v-pre class="language-html"><code><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity</span> <span class="token attr-name">ref</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>flickity<span class="token punctuation">"</span></span> <span class="token attr-name">:options</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>flickityOptions<span class="token punctuation">"</span></span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>1<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>2<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>3<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>4<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>5<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity</span><span class="token punctuation">></span></span>

<span class="token comment">&lt;!-- if you don't want to use the buttons Flickity provides --></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>button</span> <span class="token attr-name">@click</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>$refs.flickity.previous()<span class="token punctuation">"</span></span><span class="token punctuation">></span></span>Custom Previous Button<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>button</span><span class="token punctuation">></span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>button</span> <span class="token attr-name">@click</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>$refs.flickity.next()<span class="token punctuation">"</span></span><span class="token punctuation">></span></span>Custom Next Button<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>button</span><span class="token punctuation">></span></span>
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div></div></div><h3 id="configuring-with-props" tabindex="-1"><a class="header-anchor" href="#configuring-with-props" aria-hidden="true">#</a> Configuring with props</h3>
<p>Any options from Flickity can be passed a props</p>
<div class="language-html line-numbers-mode" data-ext="html"><pre v-pre class="language-html"><code><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity</span>
  <span class="token attr-name">ref</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>flickity<span class="token punctuation">"</span></span>
  <span class="token attr-name">prev-next-buttons</span>
  <span class="token attr-name">page-dots</span>
  <span class="token attr-name">wrap-around</span>
  <span class="token attr-name">:initial-index</span><span class="token attr-value"><span class="token punctuation attr-equals">=</span><span class="token punctuation">"</span>3<span class="token punctuation">"</span></span>
<span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>1<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>2<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>3<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>4<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>flickity-cell</span><span class="token punctuation">></span></span>5<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity-cell</span><span class="token punctuation">></span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>flickity</span><span class="token punctuation">></span></span>
</code></pre><div class="line-numbers" aria-hidden="true"><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div><div class="line-number"></div></div></div></div></template>


