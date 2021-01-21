- ### **1、查看npm的镜像源**

```
npm config get registry
// 默认是：https://registry.npmjs.org/
```

- ### **2、修改成淘宝的镜像源**

```
npm config set registry https://registry.npm.taobao.org
```

- ### **3、`create-react-app`创建项目**

```
npx create-react-app todolist

// npx comes with npm 5.2+，可以直接使用 npx create-react-app

// 也可以使用 npm init react-app todolist         --需要 npm 6+
```

- ### **4、启动**

```
cd todolist
npm run start
```

 