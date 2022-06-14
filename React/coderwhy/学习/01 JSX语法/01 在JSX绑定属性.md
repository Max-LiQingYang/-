```js
      function getSizeImage(url, size) {

        return url + `?size=${size}x${size}`;

      }

  

      class App extends React.Component {

        constructor() {

          super();

  

          this.state = {

            number: 0,

            imgUrl: "url",

            link: "linkurl",

            divClass: "div_class",

            active: false,

            font_size: "50px",

          };

        }

  

        render() {

          // 可以省略 this.state

          const { imgUrl, active, font_size, link } = this.state;

  

          return (

            <div>

              {/* 使用外部定义函数 */}

              <img src={getSizeImage(imgUrl, 140)} alt="" />

              <a href={link} target="_blank">

                百度一下

              </a>

              {/* 绑定class,因为 class 为关键字, 所以改为 className */}

              <div className={"box title" + (active ? "active" : "")}></div>

              {/* 绑定关键字, 因为JS有关键字 for 所以jsx改成 htmlFor */}

              <label htmlFor=""></label>

              {/* 绑定 style */}

              <div style={{ color: "red", fontSize: font_size }}>内联样式</div>

            </div>

          );

        }

      }
```