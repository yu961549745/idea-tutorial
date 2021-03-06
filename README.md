# idea-tutorial
简单的IDEA入门记录, 以 2018.2 为准

# 破解安装
[获取最新破解补丁和注册码](http://idea.lanyus.com/)

[破解补丁下载](http://idea.lanyus.com/jar/JetbrainsCrack-2.10-release-enc.jar)

在`IDEA安装位置/bin`下放入破解补丁, 修改`idea.vmoptions`文件, 增加
```
-javaagent:JetbrainsCrack-2.10-release-enc.jar
```
+ Mac 应该要先打开一次程序, 因为会有验证文件完整性的过程
+ 注意和下载的文件对应
+ Windows 需要同时设置两个`.vmoptions`文件
+ Windows 可能需要将`-javaagent`设为绝对路径
+ 打开欢迎界面 Configure -> Manage Licenses -> Activation Code 输入注册码

# 默认设置
不打开任何项目的界面 : 

## 检查默认Java SDK
Configure -> Project Defaults -> Project Structure

设置 JDK 文档
+ 官网下载 javadoc
+ Configure -> Project Defaults -> Project Structure 
![javadoc](imgs/javadoc.png)

## 设置 Maven 
Configure -> Preference -> Build Tools -> Maven -> Importing
+ 自动更新 Import Maven projects automatically
+ 自动下载源码和文档 Automatically Download: Sources and Documentation

## JavaDoc
Configure -> Preference -> Editor -> General -> Show quick documentation on mouse move

感觉体验不是很好, 还是自己 `ctrl+J` 吧

## Java 自动导入和移除包
Configure -> Preference -> Editor -> General -> Auto Import
+ 自动导包 Add unambiguous imports on the fly
+ 导包优化 Optimize imports on the fly, 会 `import java.io.*` 不推荐 

## 自动补全设置
Configure -> Preference -> Editor -> General -> Code Completion

## 显示工具栏
View -> Toolbar

## 阿里巴巴集团开发规约插件
安装流程查看[官网](http://ide.alibaba-inc.com/)

似乎顺便安装了 Hotcode 2

## 常用快捷键
+ `cmd+alt+L` 格式化代码
+ `ctrl+J` 查看文档
+ `cmd+delete` 删除当前行
+ `cmd+B`/`cmd+鼠标` 前往定义
+ `alt+enter`
    + 在包重复时提供选择
+ `cmd+N` 生成 getter / setter 
+ `cmd+F9` Build 项目
+ `cmd+Z` / `cmd+shift+Z` undo / redo
+ `cmd+F` / `cmd+R` Find / Replace

更多
[mac](https://github.com/judasn/IntelliJ-IDEA-Tutorial/blob/master/keymap-mac-introduce.md)
[win](https://github.com/judasn/IntelliJ-IDEA-Tutorial/blob/master/keymap-introduce.md)

## 从源码导入 Module
File -> New -> Module From Existing Source 

## Maven 命令学习
+ `validate` - validate the project is correct and all necessary information is available
+ `compile` - compile the source code of the project
+ `test` - test the compiled source code using a suitable unit testing framework. These tests should not require + the code be packaged or deployed
+ `package` - take the compiled code and package it in its distributable format, such as a JAR.
+ `verify` - run any checks on results of integration tests to ensure quality criteria are met
+ `install` - install the package into the local repository, for use as a dependency in other projects locally
+ `deploy` - done in the build environment, copies the final package to the remote repository for sharing with other developers and projects.

常用命令
+ `mvn clean` 清空
+ `mvn package` 打包 jar
+ `mvn install` 安装到本地仓库


## HotCode2 使用
1. 开启 IDEA 插件 (安装 阿里巴巴集团开发规约 时已自带)
2. 运行程序
3. 修改代码
4. Build 项目
