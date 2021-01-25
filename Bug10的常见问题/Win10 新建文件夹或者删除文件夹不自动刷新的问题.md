### 问题描述

前一阵子突然发现电脑出现了点问题：

当我在某个盘里新建一个文件夹之后，文件夹界面不会自动刷新，需要手动刷新一下才会显示出来，删除文件夹的时候也是如此，这个突如其来的问题让我猝不及防。

### 解决方法

修改注册表（亲测有效）:    

Win+R，调出运行窗口；    

输入 regedit，回车，打开注册表编辑器；    

点击 HKEY_LOCAL_MACHINE—SYSTEM—CurrentControlSet—Control—Update;    

点击 Update 编辑 UpdateMode 的值为0（16进制）；    

如果没有 Update，则在 Control下新建—项，命名为 Update。   

 在 Update 点击右键新建—DWORD（32位）重命名为 UpdateMode，把值修改为0；    

关闭注册表，重启系统。   

【UpdateMode 是设置是否自动刷新窗口显示，其值为1表示否，为0表示是。】



### 图示说明

![](https://cdn.jsdelivr.net/gh/aobocodoeo/imgbank@master/20210125140417.jpg)



### 新建reg文件

- 新建txt文件,在文件中键入如下内容

  ```reg
  Windows Registry Editor Version 5.00
  
  [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Update\UpdateMode]
  "DWORD"=hex(2):30,00,00,00
  ```

- 修改文件名后缀为`.reg` 双击运行即可

