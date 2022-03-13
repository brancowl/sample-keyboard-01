# Webpack

## What is webpack?
module bundler

## setting webpack

### install dependency
```
npm i -D webpack webpack-cli webpack-dev-server
```
- npm i? : npm install
- -D? : shortcut for '--save-dev'
- --save-dev? : package will appear in devDependencies
- devDependencies? : 빌드시 포함 안됨
- webpack-cli? : cli tool of webpack
- webpack-dev-server : use webpack with a development server that provides live reloading

> package-lock.json?
> after installing webpack, package-lock.json was created
what is it?
> it writes more accurate version than package.json 

```
npm i -D terser-webpack-plugin 
```
- -D? D = --save-dev
- terser-webpack-plugin : javascript 코드 난독화, debugger 구문 제거

## create webpack.config.js
``` js
const path = require("path");
const TerserWebpackPlugin = require('terser-webpack-plugin');

module.exports = {
    entry: "./src/js/index.js",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "./dist"),
        clean: true
    },
    devtool: "source-map",
    mode: "development",
    optimization: {
        minimizer: [
            new TerserWebpackPlugin()
        ]
    }
}
```
- require : node js 에서 외부 모듈을 가져오는 함수
- require("path") : it provides utilities for working with file and directory paths
- entry : 최초 짐입점
- __dirname : 현재 directory
- path.resolve(__dirname, "./dist") : __dirname/dist
- clean true : output directory 정리
- devtool : "source-map" =>  빌드 시 소스를 난독화된 소스와 원본 소스 매핑


### run webpack
```
npx webpack
```
- npx : npm 실행 도구
- npx webpack : run webpack


## html webpack

### install dependency
```
npm i -D html-webpack-plugin
```
- html 을 만들어주는 플러그인

```
npm i -D mini-css-extract-plugin css-loader css-minimizer-webpack-plugin
```
- css 를 추출해주고 압축해주는 플러그인