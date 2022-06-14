## 方式1: props

属性展开: 将祖先组件传给父祖家的 props 全部传给子组件.

![[Pasted image 20220524164800.png]]

---
## 方式2: Context 祖先与子组件的数据传递

![[Pasted image 20220524164926.png]]

函数式组件不能使用 Context.

类组件的 Context 基本使用:

![[Pasted image 20220524171051.png]]
![[Pasted image 20220524171102.png]]

在函数组件中使用 Context: **使用 Context.Consumer**

![[Pasted image 20220524173221.png]]


### 多个 Context 使用

定义两个 Context:

![[Pasted image 20220524174022.png]]

祖先组件 Provide 两个 Context:

![[Pasted image 20220524174047.png]]

**子组件 Consumer 使用 Context: (嵌套)**

![[Pasted image 20220524174125.png]]