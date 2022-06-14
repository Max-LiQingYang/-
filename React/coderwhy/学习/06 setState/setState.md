## setState 异步更新

setState 方法是从 Component 中继承过来的。

==setState() 是异步更新的！==我们并不能在执行完 setState 之后立马拿到最新的 state 的结果。

==为什么 setState 被设计为异步的？==

![[Pasted image 20220525074047.png]]

那么，**如何获取异步更新后的数据呢？**

### 方式一：

传入回调函数：`this.setState(newState, callBack)`, 从回调函数 callBack 取出的 state 是更新后的数据.


### 方式二:

在 `componentDidUpdate()` 生命周期中获取更新后的数据. **值得注意的是, 回调函数是在 `componentDidUpdate` 生命周期之后执行的.**



---
## setState 同步更新的情况

### 情况1

将 setState 放入定时器中.

```js
changeText() {
	setTimeout(() => {
		this.setState(newState, callback);
		console.log(this.state.message);  // 得到更新后的值
	}, 0);
}
```


### 情况2

使用原始 Dom 方式进行监听.

```js
componentDidMount() {
	const btnEl = document.getElementById("btn");
	btnEl.addEventListener("click", () => {
		this.setState(newState, callback);
		console.log(this.state.newState);  // 更新后的数据
	});
}
```

*总结:*

在组件生命周期或 React 合成事件中, setState 是异步的.

在定时器或者原生DOM事件中, setState 是同步的.



---
## setState 数据的合并

源码中使用 `Object.assign({}, {newState}, this.state)` 进行的数据合并. 所以新的数据不会整体覆盖 this.state, 而是合并.

**setState 合并时的注意点:**

### state 本身被合并

```js
this.state = {
	counter: 0
}

increment() {
	this.setState({
		counter: this.state.counter + 1
	})
	this.setState({
		counter: this.state.counter + 1
	})
	this.setState({
		counter: this.state.counter + 1
	})

	// 最后, this.setState.counter 是1
}
```

这是因为多次使用 this.setState 方法调用 Object.assign() 时是通过 do-while 循环调用的 Object.assign(), 每次都将旧值与新值合并, 而每次的新值都是 1, 因为 this.setState 是异步更新.


### 如果希望 setState 合并时进行累加

**给 setState 传入函数.** 如果多次使用 setState 则这个函数会被多次调用.

```js
this.setState((prevState, props) => {
	return {
		counter: prevState.count + 1
	}
})
```



