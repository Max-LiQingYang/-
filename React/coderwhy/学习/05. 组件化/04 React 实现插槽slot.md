## 方式一：

往 this.props.children 传入组件, 然后子组件调用 this.props.children 数组.

![[Pasted image 20220524162845.png]]

> 子组件
![[Pasted image 20220524162805.png]]



## 方式二:

通过 this.props.config 属性方式:

![[Pasted image 20220524163540.png]]

![[Pasted image 20220524163513.png]]