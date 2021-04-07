# 锚点定位 Anchor

## 如何使用

> 主要用于锚点定位，和tab的固定，手机端不兼容

```jsx
import { Anchor } from 'bee'

class App extends React.Component {
  render () {
    return <div>
              <div id="test1" style={{'height':'500px','background': 'red'}}>test1</div>
              <Anchor activeCls="active-cls" offsetRange={200} fixedHandle={()=>console.log('fixed!')}>
                  <div>
                      <a href="test1">test1</a>
                      <a href="test2">test2</a>
                      <a href="test3">test3</a>
                  </div>
              </Anchor>
              <div id="test2" style={{'height':'500px','background': 'gray'}}>test2</div>
              <div id="test3" style={{'height':'500px','background': '#ffeb3b'}}>test3</div>
           </div>
  }
}

```


## API
## Anchor



|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| activeCls     | active class，                                      | string  | ``null`` |
| offsetRange  | 距离窗指定偏移量后触发，                                | number  | ``null`` |
| fixedHandle  | 固定定位后的回调，                                      | function  | ``null`` |



## 实例演示
```jsx
/*react*/
<script>
const { Anchor } = bee

export default class App extends React.Component {
  render () {
    return <div>
                <Anchor activeCls="active-cls" offsetRange={200} fixedHandle={()=>console.log('fixed!')}>
                    <div style={{'display':'flex'}}>
                        <a style={{'width':'100px','height':'50px','display':'inline-block'}} href="test1">test1</a>
                        <a style={{'width':'100px','height':'50px','display':'inline-block'}} href="test2">test2</a>
                        <a style={{'width':'100px','height':'50px','display':'inline-block'}} href="test3">test3</a>
                    </div>
                </Anchor>
                <div id="test1" style={{'height':'500px','background': 'red'}}>test1</div>
                <div id="test2" style={{'height':'500px','background': 'gray'}}>test2</div>
                <div id="test3" style={{'height':'500px','background': '#ffeb3b'}}>test3</div>
           </div>
  }
}
</script>
```


## 更多
> 暂无