使用类似于 Vuex

新建 router/index.js 文件：

![[Pasted image 20220613072454.png]]

使用路由配置：

```js
import { renderRoutes } from "react-router-config";
import routes from "../router/index.js";

class Xxx extends Yyy {
	render() {
		return (
			<div>
				// 渲染路由
				{renderRoutes(routes)}
			</div>
		)
	}
}
```

渲染子路由, 及 **matchRoutes() 匹配方法：**

>注意，只有父路由通过 renderRoutes 的方式渲染路由才会在 props 中包含 route 参数。

```js
import { renderRoutes } from "react-router-config";
import routes from "../router/index.js";

class Xxx extends Yyy {
	render() {
		console.log(this.props.route);
	  // 返回你匹配到的所有路径分支
		const branch = matchRoutes(/* 用来匹配的数组 */this.props.route.routes, "/about");
		
		return (
			<div>
				// 渲染子路由
				{renderRoutes(this.props.route.routes)}
			</div>
		)
	}
}
```