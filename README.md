# jello-demo
help you build the jello-demo

## 注意node版本
 
我之前的node版本是8+，可能是因为版本过高（但不绝对），导致后续搭建环境出现了一系列的问题，如果你的node版本过高，我建议你降低你的node版本，这里推荐一个node的版本控制工具：nvm。它可以让你自由的在不同的node版本中进行切换。

## 安装 fis3

```
$ npm install fis3 -g
```

**fis3 版本必须 >= 3.2.1** 目前请通过 `npm install -g fis3@3.2.1` 安装。

## 初始化

```bash
$ mkdir demo
$ cd demo
$ fis3 init jello-demo
```

## 运行 & 预览

```bash
$ fis3 release
$ fis3 server start
```

## 发布产品代码

开启压缩和合并等等。。

```bash
$ fis3 release prod -d /path/of/your/j2ee/app
```

## 安装失败可能的原因

当你npm i某些模块的时候，npm是下载的该模块的源码，然后在本地通过编译，但是在本地进行编译时，依赖的工具可能过多，导致你编译失败，这就是为什么当你使用fis3 init jello-demo搭建项目，然后使用npm i报错，提示你需要安装.NET FrameWork和Visual Studio的原因（ps：我就是因为这个原因失败了n次。。），
你可以看到在根目录下有个.npmrc文件，这个文件中有一行sass_binary_site=https://npm.taobao.org/mirrors/node-sass/。这条语句的作用是直接将你依赖的node-sass模块编译后的代码下载下来，而不用在本地进行编译。
