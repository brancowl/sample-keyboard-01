# Webpack

## What is webpack?
module bundler

## setting webpack
```
npm i -D webpack webpack-cli webpack-dev-server
```
- npm i? : npm install
- -D? : shorcut for '--save-dev'
- --save-dev? : package will appear in devDependencies
- devDependencies? : 빌드시 포함 안됨
- webpack-cli? : cli tool of webpack
- webpack-dev-server : use webpack with a development server that provides live reloading

> package-lock.json?
> after installing webpack, package-lock.json was created
what is it?
> it writes more accurate version than package.json 

## create webpack.config.js
``` js
const path = require("path");

module.exports = {
    entry: "./src/js/index.js",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "./dist"),
        clean: true
    }
```
- require : node js 에서 외부 모듈을 가져오는 함수
- require("path") : it provides utilities for working with file and directory paths
- entry : 최초 짐입점
- __dirname : 현재 directory
- path.resolve(__dirname, "./dist") : __dirname/dist
- clean true : output directory 정리