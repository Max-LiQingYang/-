yarn add events

## 使用

创建事件总线: eventBus = new EventEmitter()

订阅监听: eventBus.addListener("事件名", handleFunction);

发出事件: eventBus.emit("event", arg1, arg2)

取消监听: eventBus.removeListener("event", handleFunction);

![[Pasted image 20220525113023.png]]

![[Pasted image 20220525114252.png]]

![[Pasted image 20220525114243.png]]