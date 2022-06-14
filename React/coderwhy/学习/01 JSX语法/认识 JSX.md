## JSX 语法

只有在引入了 babel.min.js 以及 `<script>` 元素被赋值 `type="text/babel"` 属性后才会允许存在.

```html
    <script src="../react/babel.min.js"></script>

  

    <script type="text/babel">
	    ...
    </script>
```


## 书写规范

![[Pasted image 20220520093108.png]]


## JSX 注释

```js
{/* 我是注释 */}
```



## 在 {} 中不能显示的(忽略)内容

```js
class App extends React.Component {
	constructor () {
		super();

		this.state = {
			// 以下在jsx模板中不会显示
			test1: null,
			test2: undefined,
			test3: true
		}
	}
}
```



## 对象不能作为 JSX 的子类

```js
class App extends React.Component {
	constructor () {
		super();

		this.state = {
			// 以下不允许
			friend: {
				name: "kobe"
			}
		}
	}
}
```



## {} 中可以嵌入表达式

```js
class App extends React.Component {
	constructor () {
		super();

		this.state = {
		};
	}

	render () {
		return (
			{/* 函数调用, 二元表达式, 运算符表达式, 三元表达式 */}
			{this.getFullName()}
		)
	}
}
```