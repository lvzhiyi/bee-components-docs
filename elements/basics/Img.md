# 图片加载 Img

## 如何使用

> 主要用于img占位图的使用，防止图片src不合法导致图片不显示

```jsx
import { Img } from 'bee'
const Img = require('/*  src  */');

class App extends React.Component {
  render () {
    return <Img place={Img} src={}>确认</Img>
  }
}

```


## API
## Img

> place、src优先加载src，没有src的时候加载place占位图，两者都没有的时候加载 “暂无图片~” 字样。


|   属性   |                       说明                       |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
| place/src  | 图片地址，                                      | string  | ``null`` |


## 实例演示
```jsx
/*react*/
<script>
const { Img } = bee

export default class App extends React.Component {
  render () {
    const sty = {
        'width':'300px',
        'height':'400px',
        'overflow':'hidden'
    }
    return <div style={{'display':'flex'}}>
                <div style={sty}>
                    <h4>优先加载src</h4>
                    <Img place="http://img.taopic.com/uploads/allimg/140720/240468-140H00G00341.jpg"
                        src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1525879992802&di=a4dadde161a335cec130166cec6f7cf5&    imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2Fc9fcc3cec3fdfc030223e49ede3f8794a4c226b8.jpg" />
                </div>
                <div style={sty}>
                    <h4>src不合法或者没有src加载place</h4>
                    <Img place="http://img.taopic.com/uploads/allimg/140720/240468-140H00G00341.jpg" src="1111111111" />
                </div>
                <div style={sty}>
                    <h4>两者都没有，加载暂无图片~</h4>
                    <Img place="" src="" />
                </div>
           </div>
  }
}
</script>
```


## 更多
> 暂无