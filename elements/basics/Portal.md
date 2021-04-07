# 节点入口 Portal

## 如何使用

> 主要用于需要插入到固定根节点的组件的包裹组件，比如全局提示、`modal`等组件, 兼容了react-dom 1.6.0以下不支持`createPortal`的版本

```jsx
import { Portal } from 'bee'

class App extends React.Component {
  render () {
    return <Portal container={document.getElementById('test')}>
                // you components
           </Portal>
  }
}

```
## Portal

> 插入到固定的节点container的参数将被`ReactDOM.findDOMNode(container)`接收，所以接收一个非函数式组件或者一个Element节点

|   属性   |                       说明                       |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
|  container  | 所要插入的节点位置                         | `Element` 或 `Component`  | ``body`` |

## 实例演示

<!-- > picker组件就运用了Portal组件，将节点插入至根节点 具体参见 [picker] -->

```jsx
/*react*/
<script>
//Test Portal !

export default class App extends React.Component {

    render() {
        const style1 = {
            'width': '200px',
            'height': '150px',
            'backgroundColor': 'yellowgreen'
        }
         const style2 = {
            'width': '200px',
            'height': '150px',
            'backgroundColor': 'aquamarine'
        }
        return (
            <div style={{'display':'flex','justifyContent': 'space-between'}}>
                <div id="test1" style={style1}/>
                <div id="test2" style={style2}/>
            </div>
        );
    }
}
</script>
```


```jsx
/*react*/
<script>
const { Portal } = bee
export default class App extends React.Component {

    state = {
        node:'test1'
    }

    render() {
        const style = {
            'width': '200px',
            'height': '150px',
            'backgroundColor': 'yellowgreen'
        }
        const sty = {
            'width': '50px',
            'height': '50px',
            'backgroundColor': '#3AB078'
        }
        return (
            <div style={{'display':'flex'}}>
                <button className="primary-btn" onClick={()=>this.setState({node:this.state.node === 'test1' ? 'test2' : 'test1'})}>toggle Portal</button>
                <Portal container={document.getElementById(this.state.node)}>
                    <div style={sty}>Test Portal !</div>
                </Portal>
            </div>
        );
    }
}
</script>
```


## 更多
> 暂无

