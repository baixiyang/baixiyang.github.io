---
categories: [webpack]
---
### 用法1

```
// 运行到这行代码的时候会发请求引入这个js模块
import('xxx').then(function(module){
  module = module.default
  //do something
})
```

### vue示例

```
new Vue({
  // ...
  components: {
    'my-component': () => import('./my-async-component').then(d => d.default)
  }
})
```

### CommonJS require.ensure

```
require.ensure(dependencies: String[], callback: function(require), errorCallback: function(error), chunkName: String)
```
//chunkName, 打包的块名,相同块名会打包成一个js文件



### CommonsChunkPlugin

// 例子
```
const CommonsChunkPlugin = require('webpack/lib/optimize/CommonsChunkPlugin')
{
  plugins:[
    new CommonsChunkPlugin({
      name: 'vendors',
      filename: 'assets/js/vendors.js',
      chunks: chunks,
      minChunks: chunks.length
    }),
  ]
}
```

### ExtractTextWebpackPlugin

```
const ExtractTextPlugin = require("extract-text-webpack-plugin");
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ExtractTextPlugin.extract({
          fallback: "style-loader",
          use: "css-loader"
        })
      }
    ]
  },
  plugins: [
    new ExtractTextPlugin("styles.css"),
  ]
}
```

multiple
```
const ExtractTextPlugin = require('extract-text-webpack-plugin');

// Create multiple instances
const extractCSS = new ExtractTextPlugin({
  filename:  (getPath) => {
   return getPath('css/[name]-one.css')
  },
  // 默认是false ,只会处理initial chunks, true 还会处理additional chunks
  // 使用CommonsChunkPlugin的时候会出现additional chunks
  allChunks: true
});

const extractLESS = new ExtractTextPlugin({
  filename:  (getPath) => {
    return getPath('css/[name]-two.css')
  },
  allChunks: true
});

module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ExtractTextPlugin.extract({
          use: ['css-loader', 'postcss-loader'],
          // allChunks 是false的时候,需要用style-loader来处理additional chunks中的部分
          fallback: 'style-loader'
        })
      },
      {
        test: /\.less$/,
        use: ExtractTextPlugin.extract({
          use: ['css-loader', 'postcss-loader', 'less-loader'],
          fallback: 'style-loader'
        })
      },
    ]
  },
  plugins: [
    extractCSS,
    extractLESS
  ]
};
```