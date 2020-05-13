### 本项目是cml项目在小程序端的store最佳使用方法

由于alipay小程序的限制，不支持分包之间的实例共享，导致不能共用store实例
```
// app.cml  将store挂载到全局
import routerConfig from '../router.config.json';
import store from 'store';

class App {
  data = {
    routerConfig,
    store
  }
  created(res) {
  }
}
// 主包文件使用
import store from store
// 子包使用
let store = getApp().data.store
// 直接获取state的值
getApp().data.store.state.xxxx

```