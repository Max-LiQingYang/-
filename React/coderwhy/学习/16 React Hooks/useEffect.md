## useEffect

```js
import React, { useEffect, useState } from "react";

function LearnUseEffect () {
	const [count, setCount] = useState(0);

	// useEffect 在每次渲染之后的时候调用(包括第一次)
	// 比如在 componentDidMount, componentWillUnmount 和 componentDidUpdate 时调用
	useEffect(() => {
		console.log("订阅一些事件");
	
		return () => {
			console.log("在这里取消订阅一些事件");
		}
	}, /* 第二个参数用来提高效率 */[]);

	// 可以多次调用 useEffect, 多个 useEffect 按照定义顺序执行
	useEffect(() => {
		// 第二个参数表示这个 useEffect 依赖的变量
		// 当这个变量发生改变时, useEffect 才会调用
	}, [count]);

	return <div></div>
}
```

`useEffect()` 的第二个参数表示该副作用依赖的变量, 用来性能优化.

如果我们只想让它执行一次, 那么可以给第二个参数赋值空数组.
