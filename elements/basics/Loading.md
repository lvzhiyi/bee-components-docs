# 加载 Loading

## 如何使用


```jsx
import { Loading } from 'bee'

class App extends React.Component {
  render () {
    return <Loading size="small" />
  }
}

```


## API
## Loading



|   属性   |                       说明                       |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
| color  | 组件颜色，                                           | string  | ``#ffeb3b`` |
| size  | 组件大小，可选值为 ``small default large``             | string  | ``default`` |
| tip  | loading描述，                                         | string  | ``null`` |



## 实例演示
```jsx
/*react*/
<script>
const { Loading } = bee

export default class App extends React.Component {
  render () {
    const sty = {
        'width':'300px',
        'height':'200px',
        'overflow':'hidden',
        'position': 'relative'
    }
    return <div style={{'display':'flex','position': 'relative'}}>
                <div style={sty}>
                    <Loading />
                </div>
                <div style={sty}>
                    <Loading color="grey" size="small"/>
                </div>
                <div style={sty}>
                    <Loading color="#9BD7BA" size="large" tip="loading……"/>
                </div>
           </div>
  }
}
</script>
```


## 更多
> 暂无