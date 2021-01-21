## 介绍

Node.js 是一个开源与跨平台的 JavaScript 运行时环境。 它是一个可用于几乎任何项目的流行工具！

Node.js 在浏览器外运行 V8 JavaScript 引擎（Google Chrome 的内核）。 这使 Node.js 表现得非常出色。

详见:https://nodejs.org/zh-cn/docs/



## 开始你的第一个nodejs 应用程序

> 学习参考视频:https://www.bilibili.com/video/BV1R741137Ki
>
> 视频作者:**峰华前端工程师** 
>
> 我是跟随该up主一步步学习的,若你对文本内容不感冒,可直接查看教学视频

### nodejs下载与安装

- 前往[nodejs官网](https://nodejs.org/en/)下载LTS长期支持版

- 若是Windows安装,无脑下一步

- 打开终端,输入:

  ```
  node -v 
  ```

  查看node的安装版本,也可以检测本机nodejs环境是否安装成功



### nodejs项目的创建



```shell
midir node_helloworld //创建名为node_helloworld的文件夹

cd node_helloworld //进入文件夹

npm init //初始化设置

```

![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121132500.png)



- 创建过程中,对于询问信息的**详解**

- 如果你讨厌这些烦人的信息录入 可以执行

  ```shell
  node init -y //全部以默认信息创建
  ```
  
  | package name:       | 你的项目名字叫啥 |
  | :-- | ---- |
  | **version:**        | 版本号 |
  | **description:**    | 对项目的描述 |
  | **entry point:**    | 项目的入口文件（一般你要用那个js文件作为node服务，就填写那个文件） |
  | **test command:**   | 项目启动的时候要用什么命令来执行脚本文件（默认为node app.js） |
  | **git repository:** | 如果你要将项目上传到git中的话，那么就需要填写git的仓库地址（这里就不写地址了） |
  | **keywirds：**      | 项目关键字（我也不知道有啥用，所以我就不写了） |
  | **author:**         | 作者的名字（也就是你叫啥名字） |
  | **license:**        | 发行项目需要的证书（可以写MIT） |

### 启动nodejs项目

1. 首先创建一个`index.js`的项目入口文件

2. 在js中写入一行打印helloworld的脚本语言

   ```js
   console.log('hello world');
   ```

3. 打开终端 主 Node.js 应用程序文件是 `index.js`，则可以通过键入以下命令调用它：

   ```shell
   node index.js
   ```

   当运行命令时，请确保位于包含 `app.js` 文件的目录中。

4. 直接运行 node start 运行项目 打开`package.json`文件

5. 在**"scripts"**添加启动命令**"start": "node index.js",**

   ```json
   {
     "name": "hello-world",
     "version": "1.0.0",
     "description": "This is our first nodejs application",
     "main": "index.js",
     "scripts": {
       "start": "node index.js", //添加启动命令
       "test": "echo \"Error: no test specified\" && exit 1"
     },
     "author": "GoogleX",
     "license": "MIT"
   }
   ```

6. 打开终端 则可以通过键入以下命令启动它:

   ```shell
   node start
   ```

   ![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121134614.png)