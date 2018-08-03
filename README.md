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

## Maven 项目生成 jar
`mvn install`

## TODO
+ 进一步了解 mvn 命令