---
categories: 
- 编程开发
tags:
- 前端开发
---
#### 个人使用webpack 配置

- webpack 4.0
- yarn
- 主要是单页的开发，和小项目页面开发。主要是打包js

#### package.json

```js
{
  "name": "test",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "dependencies": {
    "compass-mixins": "^0.12.10",
    "css-loader": "^3.4.2",
    "file-loader": "^5.0.2",
    "html-webpack-plugin": "^3.2.0",
    "mini-css-extract-plugin": "^0.9.0",
    "node-sass": "^4.13.1",
    "postcss-loader": "^3.0.0",
    "sass-loader": "^8.0.2",
    "ts-loader": "^6.2.1",
    "typescript": "^3.7.5",
    "url-loader": "^3.0.0",
    "webpack": "^4.41.5",
    "webpack-cli": "^3.3.10",
    "webpack-dev-server": "^3.10.1"
  },
  "scripts": {
    "start": "webpack-dev-server"
  }
}
```

#### webpack.config.js

```js
const path = require('path');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const HtmlWebpackPlugin = require('html-webpack-plugin');
module.exports = {
    entry: {
        "index": "./src/js/index.ts",
    },
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: "./js/[name].js"
    },
    plugins: [
        new MiniCssExtractPlugin({
            filename: './css/[name].css',
        }),
        new HtmlWebpackPlugin({
            filename: "index.html",
            template: "./src/index.html",
            chunks: ["index"]
        }),

    ],
    module: {
        rules: [{
                test: /\.scss$/,
                use: [{
                        loader: MiniCssExtractPlugin.loader,
                        options: {
                            publicPath: '../',
                        }
                    },
                    {
                        loader: 'css-loader',

                    },
                    'sass-loader',
                ],
            },
            {
                test: /\.(png|svg|jpg|gif)$/,
                use: [{
                    loader: 'url-loader', //是指定使用的loader和loader的配置参数
                    options: {
                        limit: 500, //是把小于500B的文件打成Base64的格式，写入JS
                        name: './imgs/[name].[ext]',
                    }
                }]
            },
            {
                test: /\.tsx?$/,
                use: 'ts-loader',
                exclude: /node_modules/,
            },
        ],
    },
    resolve: {
        extensions: ['.tsx', '.ts', '.js'],
    },
    mode: "production",
    devServer: {
        contentBase: path.join(__dirname, 'dist'),
        compress: true,
        port: 9000
    }
};
```

#### tsconfig.json

```typescript
{
  "compilerOptions": {
    "outDir": "./dist/",
    "noImplicitAny": true,
    "module": "es6",
    "target": "es5",
    "jsx": "react",
    "allowJs": true
  }
}
```

