![[Pasted image 20220613074006.png]]

![[Pasted image 20220613074424.png]]

![[Pasted image 20220613074918.png]]


## 简单例子

![[Pasted image 20220613081020.png]]

![[Pasted image 20220613081256.png]]


---
## useState 注意事项

只能通过 setState 来改变 state, 不同通过 push 等直接改变 state 的方式来改变 state, 因为 render 函数是通过判定 state 的改变来进行重新渲染的，所以 push 方式不会改变原来 state 的指向，所以不会重新渲染。

