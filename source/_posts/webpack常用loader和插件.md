---
categories: 
- 编程开发
tags:
- 前端开发
---
#### url loader

> 配置图片使用base64

```js
npm install --save-dev url-loader
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|jpg|gif)$/,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 8192
            }
          }
        ]
      }
    ]
  }
}
```

https://www.webpackjs.com/loaders/url-loader/

#### babel-loader

> 文件预处理器(用来处理es6语法什么的)

```js
npm install babel-loader@8.0.0-beta.0 @babel/core @babel/preset-env webpack
module: {
  rules: [
    {
      test: /\.js$/,
      exclude: /(node_modules|bower_components)/,
      use: {
        loader: 'babel-loader',
        options: {
          presets: ['@babel/preset-env']
        }
      }
    }
  ]
}
```

https://www.webpackjs.com/loaders/babel-loader/

#### sass-loader

> sass 编译器

```js
npm install sass-loader node-sass webpack --save-dev
module.exports = {
  module: {
    rules: [{
      test: /\.scss$/,
      use: [{
          loader: "style-loader" // 将 JS 字符串生成为 style 节点
      }, {
          loader: "css-loader" // 将 CSS 转化成 CommonJS 模块
      }, {
          loader: "sass-loader" // 将 Sass 编译成 CSS
      }]
    }]
  }
};
```



https://www.webpackjs.com/loaders/sass-loader/



#### mini-css-extract-plugin

> 将css提取到单独的文件

```js
npm install --save-dev mini-css-extract-plugin
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = {
  plugins: [
    new MiniCssExtractPlugin({
      // Options similar to the same options in webpackOptions.output
      // both options are optional
      filename: '[name].css',
      chunkFilename: '[id].css',
    }),
  ],
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          {
            loader: MiniCssExtractPlugin.loader,
            options: {
              publicPath: '/public/path/to/',
            },
          },
          'css-loader',
        ],
      },
    ],
  },
};
```

https://github.com/webpack-contrib/mini-css-extract-plugin

#### DefinePlugin

> 定义全局变量的

```
    plugins: [
		new webpack.DefinePlugin({
          'url': "xxx.com"
        });

    ],
```



https://webpack.docschina.org/plugins/define-plugin/

#### htmlwebpackplugin

> html构建工具

```
npm install --save-dev html-webpack-plugin
var HtmlWebpackPlugin = require('html-webpack-plugin');
var path = require('path');

module.exports = {
  entry: 'index.js',
  output: {
    path: path.resolve(__dirname, './dist'),
    filename: 'index_bundle.js'
  },
  plugins: [new HtmlWebpackPlugin()]
};

```



https://webpack.docschina.org/plugins/html-webpack-plugin/