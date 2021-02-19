### 前言

1. 这是利用Github+Typora+PicGo+jsDelivr这些免费的工具打造一个支持CDN加速的 markdown生产环境
2. 需要你了解Github一些简单操作和Windows的基本使用
3. 其他就没啥好说的了



### 准备与下载

1. 打开[Github](https://github.com/)官网完成注册与登录

2. 前往[Typora官网](https://www.typora.io/)下载最新版客户端Windows版

3. 访问[PicGo的github](https://github.com/Molunerfinn/PicGo/releases)下载最新版Windows客户端

   

### 新建Github仓库

1. 登录/注册GitHub，新建一个仓库，填写好仓库名，仓库描述，根据需求选择是否为仓库初始化一个README.md描述文件

   ![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050129.png)

   ![2021-01-21_035701](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050153.png)

   

2. 在主页依次选择`【Settings】-【Developer settings】-【Personal access tokens】-【Generate new token】`，填写好描述，勾选`【repo】`，然后点击【Generate token】生成一个Token，注意这个Token只会显示一次，自己先保存下来，或者等后面配置好PicGo后再关闭此网页

   ![2021-01-21_040111](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050238.png)

   ![2021-01-21_040238](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050537.png)

   ![2021-01-21_040445](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050455.png)

   ![2021-01-21_040714](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050543.png)

   ![2021-01-21_040824](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050627.png)

   

   

   

### 在Windows下配置PicGo



#### PicGo的基本配置

- 完成PicGo的安装后 打开 `PicGo -> Github` 

  ![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050638.png)

- **设定仓库名：**按照【用户名 / 图床仓库名】的格式填写

- **设定分支名：**【master】

- **设定Token：**粘贴之前生成的【Token】

- **指定存储路径：**填写想要储存的路径，如【img/】，这样就会在仓库下创建一个名为 img 的文件夹，图片将会储存在此文件夹中

- **设定自定义域名：**它的作用是，在图片上传后，PicGo会按照【`自定义域名+储存路径+上传的图片名`】的方式生成访问链接，放到粘贴板上，因为我们要使用 jsDelivr 加速访问，所以可以设置为【`https://cdn.jsdelivr.net/gh/用户名/图床仓库名@master` 】，上传完毕后，我们就可以通过【`https://cdn.jsdelivr.net/gh/用户名/图床仓库名@master/图片路径`】加速访问我们的图片了，比如：https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/windows-blue.png

- 我喜欢在仓库名后添加 @master 来指定版本,这里不添加也是可以的

  

#### 激活PicGo-Server

> 2.2.0 版本之后，PicGo 内部会默认开启一个小型的服务器，用于配合其他应用来调用 PicGo 进行上传。

1. 打开 PicGo 详细页面，进入 `PicGo -> 设置 –> 设置Server`

2. 参考下图进行设置:

   ![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121050649.png)

   

### 完成Typora的设置工作

> Typora版本 >  0.9.84

1. 进入 `文件 -> 偏好设置 -> 图像`

2. 参考图片中的进行配置:

   ![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210219122625.jpg)

3. 验证图片上传(查看是否成功)

   ![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/2021-01-21_043712.png)





### 使用篇

> 上面的设置完成后，在 Typora 里写字时，就可以自动上传图片到图床啦。

- **拖拽:** 可以直接选择图片，然后拖拽到编辑页面。

  ![aHR0cDovL2hveGlzLmliZXRhbGlmZS5jb20vcGljZ28vMjAyMDAzMTAxMzAzMDIuZ2lm](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/aHR0cDovL2hveGlzLmliZXRhbGlmZS5jb20vcGljZ28vMjAyMDAzMTAxMzAzMDIuZ2lm.gif)

- **编辑器内插入:** 使用快捷键 **Ctrl + Shift + I**，可以调出插入图片的功能。(常用功能)

  ![aHR0cDovL2hveGlzLmliZXRhbGlmZS5jb20vcGljZ28vMjAyMDAzMTAxMzQxMTIuZ2lm](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/aHR0cDovL2hveGlzLmliZXRhbGlmZS5jb20vcGljZ28vMjAyMDAzMTAxMzQxMTIuZ2lm.gif)

- **复制粘贴:** 也可以直接复制图片，然后再编辑器中直接粘贴。

  

- **截图后直接粘贴:** 比如使用Snipaste
![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/aHR0cDovL2hveGlzLmliZXRhbGlmZS5jb20vcGljZ28vMjAyMDAzMTAxNTEwMzQuZ2lm.gif)



### 完结与心得

- 用法其实尽可能的在满足自己二次配置中减少时间而作,可能有许多不完善的地方
- 参考了网络上一些大佬的文章 借鉴 [hoxis](https://blog.csdn.net/bruce_6/article/details/104821531) [TRHX • 鲍勃](https://blog.csdn.net/qq_36759224/article/details/98058240) 比较多
- 不得不说配置完成以后,相当好用

