![[Pasted image 20220529105302.png]]

## 定义函数 connect 来连接组件与仓库

### 组件中：

![[Pasted image 20220530085811.png]]
![[Pasted image 20220530085823.png]]


### connect.js

![[Pasted image 20220530085856.png]]
![[Pasted image 20220530085914.png]]


---
## 使得 connect.js 更加独立，*成为一个库函数*

新建 context.js

在根组件 index.js 中使用 context 来传入 store, 这样 connect.js 以及所有的页面就不依赖 store 了, 而且不用重新导入 store.

**index.js**

![[Pasted image 20220530093157.png]]

**connect.js**

>注意: constructor(props, context) 的第二个参数是 context

![[Pasted image 20220530093230.png]]
![[Pasted image 20220530093328.png]]

