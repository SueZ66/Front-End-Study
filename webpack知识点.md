## ***webpack***知识点

### 目录

<ol>
    <li><a href="#个人见解">个人见解</a></li>
    <li><a href="#使用方法">使用方法</a>
        <ol>
            <li><a href="#项目初始化">项目初始化</a></li>
            <li><a href="#webpack开发插件">webpack开发插件</a></li>
        </ol>
    </li>
</ol>



### 个人见解

***webpack***是一款前端打包工具，可依靠各种插件的支持，将各类主流开发工具所得资源打包成***".js"***,***".html"***,***".png"***,***".jpg"***这四种格式，既能减少项目体积，又方便对模块进行解耦，能很好的协助模块化开发。



### 使用方法

#### 项目初始化

使用***npm***进行项目初始化

```shell
$ npm init
```

安装***webpack***到项目，在***webpack4***之后需要同时安装***webpack-cli***

```shell
$ npm i webpack -D
$ npm i webpack-cli -D
```

***webpack***打包命令

```shell
$ webpack --mode development //以开发者模式打包
$ webpack --mode production //以生产模式打包
```



#### ***webpack***开发插件

| 插件功能                  | 插件名称                                                     | 备注                   |
| ------------------------- | ------------------------------------------------------------ | ---------------------- |
| 以开发者模式运行调试      | [webpack-dev-server](https://github.com/webpack/webpack-dev-server) |                        |
| 将sass文件进行编译成css   | [sass-loader](https://github.com/webpack-contrib/sass-loader) |                        |
| sass文件node运行环境      | [node-sass](https://github.com/sass/node-sass)               |                        |
| 处理css文件的引入         | [css-loader](https://github.com/webpack-contrib/css-loader)  |                        |
| 将样式注入DOM中           | [style-loader](https://github.com/webpack-contrib/style-loader) |                        |
| 处理样式中的url引用       | [resolve-url-loader](https://github.com/bholloway/resolve-url-loader) |                        |
| css3兼容前缀处理          | [autoprefixer](https://github.com/postcss/autoprefixer)      |                        |
| 👆                         | [postcss-loader](https://github.com/postcss/postcss-loader)  | autoprefixer的配套插件 |
| 打包前清除dist文件夹      | [clean-webpack-plugin](https://github.com/johnagan/clean-webpack-plugin) |                        |
| 对webpack中的html进行处理 | [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |
|                           |                                                              |                        |



