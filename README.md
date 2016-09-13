
```javascript
- web-cli/
  + package.json  //npm配置文件
  + config.js //app配置文件
  + index.html //入口html
  - node_modules //npm加载的模块
  - bulid //build文件夹
  	+ css-loaders.js //文件加载器
  	+ dev-client.js //热加载配置
  	+ dev-server.js //dev环境server
  	+ webpack.base.conf.js //webpack基础
  	+ webpack.dev.conf.js //dev环境webpack
  	+ webpack.prod.conf.js //生产环境webpack
  - config 配置文件
  	+ dev.env.js //dev环境配置参数
  	+ prod.env.js //生产环境参数
  - dist
  	+  //打包之后的文件内容
  -src
  	- assets //图片
  	- common //通用配置
  		+ page.js //分页配置
  		+ routers.js //路由配置
  	- components //组件
  		- other //不可复用组件
  			+ createDp.vue //创建dp
  			+ dataPool.vue //datapool
  			+ dataPoolDetails.vue //ddataPool详情
  			+ dataPoolDetailsList.vue //dataPool详情列表
  			+ repoDetails.vue //repo详情
  		- reusable //可复用组件
  			+ button.vue //按钮组件
  			+ mCreatedp.vue //创建dp模态框
  			+ mDeletedp.vue //删除dp模态框
  			+ modal.vue //模态框
  - vuex 公共状态池
  	- modules 
  		+ dp_item.js //dp中item 列表
  		+ title_src //公共路径
  	- actions.js
  	- getters.js
  	- mutation-types.js
  	- store.js 
  - static //静态资源
  - test //测试
  	- e2e //端对端测试
  	- unit //单元测试
 
```