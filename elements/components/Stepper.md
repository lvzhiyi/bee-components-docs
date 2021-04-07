# 步进器 Stepper

## 如何使用


```jsx
import { Stepper } from 'bee'

class Test extends Component {
    render() {
        return (
            <div>
                <h3>步进器</h3>
                <Stepper min={-5} value={1.7} max={10} step={0.9}/>
                <Stepper max={20} step={2}/>
                <Stepper disabled max={20} step={2}/>
            </div>
        );
    }
}

```

## API
## Stepper
> 支持小数

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| value      | 默认值，                                               | number  | ``null`` |
| step       | 步进数，                                                 | number  | 1 |
| min        | 最小值                                                   | number  | 1 |
| max        | 最大值                                                   | number  | ``null`` |
| onChange   | 数值改变时的回调   ``(params:value)=>{}``                 | function  | ``null`` |
| onButtonClick | 点击增减按钮时的回调 ``(params:value)=>{}``            | function  | ``null`` |


## 实例演示
```jsx
/*react*/
<script>
const { Stepper } = bee

export default class App extends React.Component {

    render() {
        const style={
            'width':'100%',
            'display':'flex',
            'justify-content': 'space-between'
        }
        return (
            <div>
                <div style={style}>
                    <Stepper max={20} step={2}/>
                </div>
            </div>
        );
    }
}
</script>
```
```jsx
/*react*/
<script>
const { Stepper } = bee

export default class App extends React.Component {

    render() {
        const style={
            'width':'100%',
            'display':'flex',
            'justify-content': 'space-between'
        }
        return (
            <div>
                <div style={style}>
                    <Stepper min={-5} value={1.7} max={10} step={0.9}/>
                </div>
            </div>
        );
    }
}
</script>
```
```jsx
/*react*/
<script>
const { Stepper } = bee

export default class App extends React.Component {

    render() {
        const style={
            'width':'100%',
            'display':'flex',
            'justify-content': 'space-between'
        }
        return (
            <div>
                <div style={style}>
                    <Stepper disabled max={200} value={100} step={2}/>
                </div>
            </div>
        );
    }
}
</script>
```



## 更多
> 暂无