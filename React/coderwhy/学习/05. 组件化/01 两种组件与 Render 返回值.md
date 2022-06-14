## 类组件

```js
import React, { Component } from "react";

// 类组件

export default class App extends Component {

  constructor () {

    super();
    this.state = {
    };

  }

  render () {

    return (

      <h2>

        01_App

      </h2>

    )
  }
}
```


---
## 函数组件

![[Pasted image 20220524114217.png]]

---
### 函数式组件可以 return 什么（render 函数的返回值）

当 render 被调用时，他会检查 this.props 和 this.state 的变化并返回以下类型之一：

![[Pasted image 20220524135929.png]]

