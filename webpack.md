# webpack 基础篇

## 1、webpack环境安装

 1. 新建一个目录执行`npm init -y`

 2. 在项目中安装webpack（webpack4.0以上需要同时安装webpack-cli）

    `npm install webpack webpack-cli --save-dev`

## 2、webpack简单打包

​			1.创建webpack.config.js

​					主要配置entry 入口文件、output输出位置、开发环境

			2. 在packjson中配置打包命令，在"script"标签中增加配置项

## 3、entry入口文件配置

​			1. 分为两种情况（单入口、多入口）

​				单入口适用单页面应用（entry以字符串的方式适用），多入口适用多页应用（entry以object的方式进行配置）

## 4、output配置

			1. output单入口多入口都是一个，单入口方式打包出去的filename可以写死，多入口文件可以通过[name]这种占位符的方式进行控制

## 5、loaders处理

​			作用是通过loaders这种方式吧框架指令、es语法等等一些webpack不是别的内容转化为webpack支持的语法，然后进行打包（webpack开箱即用支持js和json这种文件类型）

​		目前常见loaders 

​				babel-loader 转换es语法

​				css-loader 解析.css文件加载与解析

​				less-loader 解析.less文件转化css

​				ts-loader ts转js

​				thread-loader 多进程打包



1. 配置方法

   1. 在module下 rules里面增加匹配规则

      rules: [

      ​	{test: /\ .scss$/, use: 'scss-loader'}

      ]

   这种方式配置loader解析匹配规则

## 6、plugins插件

​	plugins是webpack的插件，用来扩扎webpack本省不具有的功能，完成例如相同代码提取为公共js、文件目录树清除等等一些功能（还有很多）

  1. 常见的plugins

       		1. CommonsChunkPlugin 讲chunks相同的模块打包成公共的js
       		2. ClearWebpackPlugin 清理构建目录
       		3. ExtracTextWebpackPlugins 讲css从bundle文件里提取成一个独立的css文件

     等等.......

		2. 使用方法，将定义好的plugin在plugins数组中写入即可

     ​	`plugins: [ new HtmlWebpackPlugins({template: './src/index.html'})]`

## 7、mode环境指定

  		1. mode是用来指定当前构建环境是development、production还是none，默认值为production
  		2. 



​			





