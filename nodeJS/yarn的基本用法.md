### ✅Yarn 的优点

与npm相比，yarn有着众多的优势，主要的优势在于：执行校验，并行执行，离线模式，版本控制。

**1、执行校验**

------

 Yarn会在每个安装包被执行前校验其完整性。

**2、并行执行**

------

npm会等一个包完全安装完才跳到下一个包，但yarn会并行执行包，因此速度会快很多。网上有不少比较npm和yarn安装同样多依赖的执行速度，yarn在速度方面优势明显。

**3、离线模式**

------

离线的原理比较简单，安装过的包会被保存进缓存目录，以后安装就直接从缓存中复制过来，这样做的本质还是会提高安装下载的速度，避免不必要的网络请求。

**4、版本控制**

------

npm用下来比较强的一个痛点就是：当包的依赖层次比较深时，版本控制不够精确。会出现相同package.json，但不同人的电脑上安装出不同版本的依赖包，出现类似 “我电脑上是好的，没问题呀”的bug很难查找。你可以使用[npm-shrinkwrap](https://link.jianshu.com/?t=https://docs.npmjs.com/cli/shrinkwrap)来实现版本固化，版本信息会写入npm-shrinkwrap.json文件中，但它毕竟不是npm的标准配置。

而yarn天生就能实现版本固化。会生成一个类似npm-shrinkwrap.json的yarn.lock文件，文件内会描述包自身的版本号，还会锁定所有它依赖的包的版本号：yarn.lock存储这你的每个包的确切依赖版本，能确保从本地开发到生产环境，所有机器上都有精确相同的依赖版本。



### ✅安装yarn 

新版的yarn安装十分方便.但是在Windows中会引发一个文件(后面会说到)

- 打开终端 键入如下命令完成安装

  ```shell
  npm install -g yarn //全局安装yarn
  ```

- 国内如果下载速度过于缓慢 可更改源地址为淘宝源

  ```shell
  yarn config set registry https://registry.npm.taobao.org -g
  
  yarn config set sass_binary_site http://cdn.npm.taobao.org/dist/node-sass -g
  ```

  

### ✅安装本地/局部包 

安装后 即可使用`yarn`的初始化命令:

```shell
yarn --version //查看本机yarn版本

mkdir yarn_demo

cd yarn_demo

yarn init //初始化项目,信息录入与npm init类似

```

**在Windows下** 安装`yarn`后 进入项目目录 使用 `yarn add ramda` 命令时会报如下错误:

![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121150736.png)

因为在此系统上禁止运行未签名脚本

**解决方案:**

```
1. 以管理员身份运行PowerShell
2. 执行：get-ExecutionPolicy，回复Restricted，表示状态是禁止的
3.执行：set-ExecutionPolicy RemoteSigned
4.选择Y
注意：一定要以管理员的身份运行PowerShell，不是cmd窗口！
```



### ✅yarn的常用命令：

- 安装yarn

  - `npm install -g yarn`

- 安装成功后，查看版本号：

  - `yarn --version`

- 创建文件夹 yarn

  - `md yarn`

- 进入yarn文件夹

  - `cd yarn`

- 初始化项目

  - `yarn init // 同npm init，执行输入信息后，会生成package.json文件`

- yarn的配置项：

  - `yarn config list // 显示所有配置项`
  - `yarn config get <key> //显示某配置项`
  - `yarn config delete <key> //删除某配置项`
  - `yarn config set <key> <value> [-g|--global] //设置配置项`

- 安装包：

  - `yarn install //安装package.json里所有包，并将包及它的所有依赖项保存进yarn.lock`
  - `yarn install --flat //安装一个包的单一版本`
  - `yarn install --force //强制重新下载所有包`
  - `yarn install --production //只安装dependencies里的包`
  - `yarn install --no-lockfile //不读取或生成yarn.lock`
  - `yarn install --pure-lockfile //不生成yarn.lock`

- 添加包（会更新package.json和yarn.lock）：

  - `yarn add [package] // 在当前的项目中添加一个依赖包，会自动更新到package.json和yarn.lock文件中`
  - `yarn add [package]@[version] // 安装指定版本，这里指的是主要版本，如果需要精确到小版本，使用-E参数`
  - `yarn add [package]@[tag] // 安装某个tag（比如beta,next或者latest）`

  //不指定依赖类型默认安装到dependencies里，你也可以指定依赖类型：

  - `yarn add --dev/-D // 加到 devDependencies`
  - `yarn add --peer/-P // 加到 peerDependencies`
  - `yarn add --optional/-O // 加到 optionalDependencies`

  //默认安装包的主要版本里的最新版本，下面两个命令可以指定版本：

  - `yarn add --exact/-E // 安装包的精确版本。例如yarn add foo@1.2.3会接受1.9.1版，但是yarn add foo@1.2.3 --exact只会接受1.2.3版`
  - `yarn add --tilde/-T // 安装包的次要版本里的最新版。例如yarn add foo@1.2.3 --tilde会接受1.2.9，但不接受1.3.0`

- 发布包

  - `yarn publish`

- 移除一个包

  - `yarn remove <packageName>：移除一个包，会自动更新package.json和yarn.lock`

- 更新一个依赖

  - `yarn upgrade 用于更新包到基于规范范围的最新版本`

- 运行脚本

  - `yarn run 用来执行在 package.json 中 scripts 属性下定义的脚本`

- 显示某个包的信息

  - `yarn info <packageName> 可以用来查看某个模块的最新版本信息`

- 缓存

  - ```
    yarn cache
    ```

    - `yarn cache list # 列出已缓存的每个包 yarn cache dir # 返回 全局缓存位置 yarn cache clean # 清除缓存`

### ✅npm 与 yarn命令比较:

![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121151844.png)


### ✅yarn.lock文件格式:

> 大家会看到，这个文件已经把依赖模块的版本号全部锁定，当你执行yarn install的时候，yarn会读取这个文件获得依赖的版本号，然后依照这个版本号去安装对应的依赖模块，这样依赖就会被锁定，以后再也不用担心版本号的问题了。其他人或者其他环境下使用的时候，把这个yarn.lock拷贝到相应的环境项目下再安装即可。
> 注意：这个文件不要手动修改它，当你使用一些操作如yarn add时，yarn会自动更新yarn.lock。

![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210121151854.png)