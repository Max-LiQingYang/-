![[Pasted image 20220525082030.png]]


## React 更新流程的 diff 算法

![[Pasted image 20220525082324.png]]

![[Pasted image 20220525082340.png]]
![[Pasted image 20220525082354.png]]
![[Pasted image 20220525082405.png]]


---
## render 函数被调用

什么时候组件的 render 函数被调用呢?

1. 第一次创建组件时;
2. 依赖的数据 (state, props) 发生变化时.

**如何控制 render 方法是否被调用?**

*对于类组件:*

### shouldComponentUpdate()

![[Pasted image 20220525084156.png]]

```js
shouldComponentUpdate(nextProps, nextState) {
	if (this.state.counter !== nextState.counter) return false;
	return true;
}
```

shouldComponentUpdate 中 state/props 的比较是浅层比较.

不要在 shouldComponentUpdate 中进行深层比较, 因为这样很浪费性能.


### PureComponent

![[Pasted image 20220525084436.png]]

```js
class MyComponent extends PureComponent {
	constructor (props) {
		super(props);
		this.state = {};
	}
	
	render () {
		return (//,,,)
	}
}
```

此时, 当组件中的 state/props 发生变化是才会调用 render 函数.

*对于函数式组件:*


### memo

```js
import React, { memo } from "react";

const MemoMyComponent = memo(function MyComponent() {
		console.log("myComponent 被调用");
		return (
			//...		
		)
});
```