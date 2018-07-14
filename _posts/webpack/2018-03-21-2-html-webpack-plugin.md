---
categories: [webpack]
---
### 可以自动生成html文件,自动引入js,还支持模板语法,

### 用法:
```
npm install HtmlWebpackPlugin -D
```

```
const HtmlWebpackPlugin = require('html-webpack-plugin')
{
  plugins:[new HtmlWebpackPlugin(options)]
}
```

### 示例

```
const HtmlWebpackPlugin = require('html-webpack-plugin')
{
  plugins:[new HtmlWebpackPlugin({
    tempate: './index.html',
    insert: 'body'
  })]
}
```

### options字段
|Name|Type|Default|Description|
|:--:|:--:|:-----:|:----------|
|**[`title`](#)**|`{String}`|``|The title to use for the generated HTML document|
|**[`filename`](#)**|`{String}`|`'index.html'`|The file to write the HTML to. Defaults to `index.html`. You can specify a subdirectory here too (eg: `assets/admin.html`)|
|**[`template`](#)**|`{String}`|``|`webpack` require path to the template. Please see the [docs](https://github.com/jantimon/html-webpack-plugin/blob/master/docs/template-option.md) for details|
|**[`inject`](#)**|`{Boolean\|String}`|`true`|`true \|\| 'head' \|\| 'body' \|\| false` Inject all assets into the given `template` or `templateContent`. When passing `true` or `'body'` all javascript resources will be placed at the bottom of the body element. `'head'` will place the scripts in the head element|
|**[`favicon`](#)**|`{String}`|``|Adds the given favicon path to the output HTML|
|**[`minify`](#)**|`{Boolean\|Object}`|`true`|Pass [html-minifier](https://github.com/kangax/html-minifier#options-quick-reference)'s options as object to minify the output|
|**[`hash`](#)**|`{Boolean}`|`false`|If `true` then append a unique `webpack` compilation hash to all included scripts and CSS files. This is useful for cache busting|
|**[`cache`](#)**|`{Boolean}`|`true`|Emit the file only if it was changed|
|**[`showErrors`](#)**|`{Boolean}`|`true`|Errors details will be written into the HTML page|
|**[`chunks`](#)**|`{?}`|`?`|Allows you to add only some chunks (e.g only the unit-test chunk)|
|**[`chunksSortMode`](#plugins)**|`{String\|Function}`|`auto`|Allows to control how chunks should be sorted before they are included to the HTML. Allowed values are `'none' \| 'auto' \| 'dependency' \| 'manual' \| {Function}`|
|**[`excludeChunks`](#)**|`{String}`|``|Allows you to skip some chunks (e.g don't add the unit-test chunk)|
|**[`xhtml`](#)**|`{Boolean}`|`false`|If `true` render the `link` tags as self-closing (XHTML compliant)|