# 轻提示 Toast

## 如何使用


```jsx
import { Toast } from 'bee'

class App extends React.Component {
  render () {
    onSubmit(){
        Toast('信息填写不完整！')
    }
    return  ……
  }
}

```

> 可以对`Toast`进行全局配置，修改默认参数

```jsx

Toast.config({
    msg:'警告',
    animate:'tada',
    timer: 5000
});

```

## API
## Toast
  > 函数调用 Toast(`msg : string | HtmlElement`,`animate`,`timer : 提示时间`), animate参数引用[animate.css](https://daneden.github.io/animate.css/)的class作为参数

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| msg     | 提示信息，                                               | string  | ``null`` |
| animate  | animate动画class，                                      | number  | bounce |
| timer  | 提示时间                                                   | number  | 2000 |

## 实例演示
```jsx
/*react*/
<script>
const { Toast } = bee

export default class App extends React.Component {

  render () {
    return <div><button className="primary-btn" onClick={()=>{Toast('test Toast!')}}>Toast</button></div>
  }
}
</script>
```

### 全局配置

```jsx
/*react*/
<script>
const { Toast } = bee;

const config = Toast.config;
config({
    msg:'警告',
    animate:'shake',
    timer: 3000
});

export default class App extends React.Component {


  render () {
    return <div><button className="primary-btn" onClick={()=>{Toast();config({})}}>Toast</button></div>
  }
}
</script>
```


## 更多
> 暂无