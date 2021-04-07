# 开关 Switch

## 如何使用


```jsx
import { Switch } from 'bee'

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
            <Switch checked={this.state.checked} onChange={this.onChange}/>
        )
    }
}

```
## Switch


|   属性   |                       说明                       |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
|  checked  | switch开关状态                                 | `boolean`  | ``true`` |
|  color  | switch开关颜色                                  | `string`  | ``#4CD964`` |
|  onChange  | 点击开关时的回调 `(value)=>{}`                 | `function`  | ``null`` |
|  disabled  | 不可点击                                      | `boolean`  | ``fasle`` |



## 实例演示


```jsx
/*react*/
<script>
const { Switch } = bee

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
            <div>
                <Switch checked={this.state.checked} onChange={this.onChange}/>
            </div>
        )
    }
}
</script>
```

#### color
```jsx
/*react*/
<script>
const { Switch } = bee

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
            <div>
                <Switch color='#e96858' checked={this.state.checked} onChange={this.onChange}/>
            </div>
        )
    }
}
</script>
```
#### disabled
```jsx
/*react*/
<script>
const { Switch } = bee

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
            <div>
                <Switch disabled checked={this.state.checked} onChange={this.onChange}/>
            </div>
        )
    }
}
</script>
```

## 更多
> 暂无

