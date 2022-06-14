## Babel

Babel 帮助我们将 `const x = <h2></h2>` 类似的语法转换成: `React.createElement(标签, 配置, children)`

![[Pasted image 20220523073353.png]]

![[Pasted image 20220523074709.png]]


---
## 虚拟 DOM 的创建过程

==通过 React.createElement 最终创建出一个 ReactElement 对象, 而 ReactElement 对象组建成一个 JS 对象树, 也就是虚拟 DOM!==

最后 虚拟DOM 通过 ReactDOM.render() 映射到真实 DOM 中.

jsx ==> React.createElement() ==> ReactElement 对象 ==> ReactDOM.render() ==> 真实 DOM

通过 ReactDOM.render() 让虚拟 DOM 和 真实 DOM 同步起来的过程叫做协调(Reconciliation).


---
## *为什么使用虚拟 DOM*

![[Pasted image 20220523075530.png]]


---
