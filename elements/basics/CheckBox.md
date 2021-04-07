# 复选按钮 CheckBox

## 如何使用


```jsx
import { CheckBox } from 'bee'

class App extends React.Component {
    state = {
        checked:true
    }
    onChange=(s)=>{
        console.log(s)
        this.setState({checked:!this.state.checked})
    }
    render(){
        return(
            <CheckBox checked={this.state.checked} onChange={this.onChange}/>
        )
    }
}

```
## CheckBox


|   属性   |                       说明                       |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
|  checked  | CheckBox开关状态                                 | `boolean`  | ``true`` |
|  className  | 自定义class,CheckBox颜色,尺寸等                  | `string`  | ``null`` |
|  onChange  | 点击开关时的回调 `(value)=>{}`                 | `function`  | ``null`` |
|  disabled  | 不可点击                                      | `boolean`  | ``fasle`` |




## 实例演示


```jsx
/*react*/
<script>
const { CheckBox } = bee
export default class App extends React.Component {
    state = {
        checked:true
    }
    onChange=(s)=>{
        console.log(s)
        this.setState({checked:!this.state.checked})
    }
    render(){
        return(
            <CheckBox checked={this.state.checked} onChange={this.onChange}/>
        )
    }
}
</script>
```
#### disabled
```jsx
/*react*/
<script>
const { CheckBox } = bee
export default class App extends React.Component {
    state = {
        checked:true
    }
    onChange=(s)=>{
        console.log(s)
        this.setState({checked:!this.state.checked})
    }
    render(){
        return(
            <CheckBox disabled checked={this.state.checked} onChange={this.onChange}/>
        )
    }
}
</script>
```

## 更多
> 暂无

