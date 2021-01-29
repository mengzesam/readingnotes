# 各种http server #
****
1. ## serve
  ```
  npm install -g serve
  ````
  然后进入一个包含有网页的文件夹运行
  serve则启动一个http服务器,

2. ## cli-service-global 
```
  npm install -g @vue/cli @vue/cli-service-global
  # or
  yarn global add @vue/cli @vue/cli-service-global
```
然后进入一个目录，包含有main.js或index.js或App.vue的文件夹运行
```
	vue serve 
```

或You can also explicitly specify the entry file:
```
	vue serve MyComponent.vue
```

3. ## 快速原型搭建
```
vue create myproject
cd myproject
npm run serve或
yarn serve
```

4、自己利用node的http模块搭建server.js

5、npm install -g http-server
```
http-server -p 8080
```