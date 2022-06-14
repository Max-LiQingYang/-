yarn add redux

对于 node 不能使用 ES6 引入 redux。

![[Pasted image 20220529103126.png]]


## store 文件夹的目录结构划分

![[Pasted image 20220529103159.png]]

## 基础使用

1. 初始化 state
2. 创建 active 与 state 映射的 reducer
3. store = redux.createStore(reducer)
4. 创建 action: {type: "xx", 参数}
5. 通过 store.dispatch(action) 来触发修改

![[Pasted image 20220529102119.png]]
![[Pasted image 20220529102135.png]]

**订阅与取消订阅**

```js
componentDidMount() {
	this.unsubscribe = store.subscribe(() => {
		this.setState({
			counter: store.getStore().counter
		});
	});	
}

// 取消订阅
componentWillUnmount() {
	this.unsubscribe();
}
```