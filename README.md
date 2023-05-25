# vue-element-admin

搭建后台管理系统，记录一些常用功能的解决技巧。

- 选择 scss 是因为可以通过引入 elementui 的 scss 文件实现样式自定义。
- 添加完 `.prettierrc.json` 文件之后需要重启 VSCode，不然没有效果。

`.nvmrc`配置当在使用`nvm use`和`nvm install`时不需要传入 version。

## 在 Vue 项目中使用 SVG 图标

### Web 设计新趋势: 使用 SVG 代替 Web Icon Font

(IO METER)[https://io-meter.com/2014/07/20/replace-icon-fonts-with-svg/]

Icon Font 的主要缺陷有以下几条：

1. 浏览器将其视为文字进行抗锯齿优化，有时得到的效果并没有想象中那么锐利。 尤其是在不同系统下对文字进行抗锯齿的算法不同，可能会导致显示效果不同。
2. Icon Font 作为一种字体，Icon 显示的大小和位置可能要受到 font-size、line-height、word-spacing 等等 CSS 属性的影响。 Icon 所在容器的 CSS 样式可能对 Icon 的位置产生影响，调整起来很不方便。
3. 使用上存在不便。首先，加载一个包含数百图标的 Icon Font，却只使用其中几个图标，非常浪费加载时间。 自己制作 Icon Font 以及把多个 Icon Font 中用到的图标整合成一个 Font 也非常不方便。
4. 为了实现最大程度的浏览器支持，可能要提供至少四种不同类型的字体文件。包括 TTF、WOFF、EOT 以及一个使用 SVG 格式定义的字体。

### SVG Defs/Symbols

```html
<svg class="icon">
  <use xlink:href="/img/posts/svg-icons.svg#circle-check"></use>
</svg>
```

SVG Icons 作为一种 Icon Font 的替代，使用上具有灵活性好、显示效果好、可控性强等诸多优点。 尤其是最后介绍的 SVG Defs/Symbols 这种方式，已经让 SVG Icon 变成了一种实用的解决方案。

### 实现方案

使用第三方库：

- 在 Vue 项目中使用第三方库（如 vue-svg-icon、vue-svg-loader 等），这些库提供了更方便的方式来使用 SVG 图标。
