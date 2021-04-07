# 拖动table ResizableTable

## 如何使用
```jsx
import { ResizableTable } from 'bee-react'

export default class App extends React.Component {
    render () {
        return <ResizableTable
                    liveDrag={true}
                >
                    <table>
                        <thead>
                        <tr>
                            <th>#</th>
                            <th>First Name</th>
                            <th>Last Name</th>
                            <th>Username</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <th>1</th>
                            <td>Mark</td>
                            <td>Otto</td>
                            <td>@mdo</td>
                        </tr>
                        <tr>
                            <th>2</th>
                            <td>Jacob</td>
                            <td>Thornton</td>
                            <td>@fat</td>
                        </tr>
                        <tr>
                            <th>3</th>
                            <td>Larry</td>
                            <td>the Bird</td>
                            <td>@twitter</td>
                        </tr>
                        </tbody>
                    </table>
                </ResizableTable>
    }
}
```


## API
## ResizableTable
|   属性   |                       说明                                    |  类型   |   默认值    |
| -------- | ------------------------------------------------------------ | ------- | ----------- |
| liveDrag | 是否启用实时拖动，                                                | boolean  | ``true`` |
| defaultMinWidth | 默认每列最小宽度，                                          | number  | 30  |
| headerOnly | 规定拖动竖线是否只有thead                                           | boolean | ``true`` |
| disabledColumns | 规定不能拖动的th                                           | arr | ``null`` |
| onResizing | 正在拖动时候的回调                                              | Funtion | ``null`` |
| onResized | 拖动结束后的回调                                               | Funtion | ``null`` |

### 特别说明：若为单独的每列设置最小宽度，需在``th``上设置自定义属性``data-min-width="number"``;


## 实例演示

### liveDrag true
```jsx
/*react*/
<script>
const { ResizableTable } = bee
export default class App extends React.Component {
    render () {
        return <ResizableTable
                    liveDrag={true}
                    defaultMinWidth={30}
                    headerOnly={true}
                    disabledColumns={[]}
                    onResizing={()=>{console.log('Resizing……')}}
                    onResized={()=>{console.log('Resized')}}
                >
                    <table style={{'width':'100%'}}>
                        <thead>
                        <tr>
                            <th>#</th>
                            <th style={{'width':'200px'}}>First Name</th>
                            <th style={{'width':'300px'}}>Last Name</th>
                            <th style={{'width':'200px'}}>Username</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <th>1</th>
                            <td>Mark</td>
                            <td>Otto</td>
                            <td>@mdo</td>
                        </tr>
                        <tr>
                            <th>2</th>
                            <td>Jacob</td>
                            <td>Thornton</td>
                            <td>@fat</td>
                        </tr>
                        <tr>
                            <th>3</th>
                            <td>Larry</td>
                            <td>the Bird</td>
                            <td>@twitter</td>
                        </tr>
                        </tbody>
                    </table>
                </ResizableTable>
    }
}
</script>
```
### liveDrag fasle
```jsx
/*react*/
<script>
const { ResizableTable,Toast } = bee
export default class App extends React.Component {
    render () {
        return <ResizableTable
                    liveDrag={false}
                    defaultMinWidth={30}
                    headerOnly={false}
                    disabledColumns={[2]}
                    onResizing={()=>{console.log('Resizing……')}}
                    onResized={()=>{console.log('Resized')}}
                >
                    <table style={{'width':'100%'}}>
                        <thead>
                        <tr>
                            <th>#</th>
                            <th style={{'width':'200px'}} data-min-width={200}>First Name</th>
                            <th style={{'width':'300px'}}>Last Name</th>
                            <th style={{'width':'200px'}}>Username</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr>
                            <th>1</th>
                            <td>Mark</td>
                            <td>Otto</td>
                            <td>@mdo</td>
                        </tr>
                        <tr>
                            <th>2</th>
                            <td>Jacob</td>
                            <td>Thornton</td>
                            <td>@fat</td>
                        </tr>
                        <tr>
                            <th>3</th>
                            <td>Larry</td>
                            <td>the Bird</td>
                            <td>@twitter</td>
                        </tr>
                        </tbody>
                    </table>
                </ResizableTable>
    }
}
</script>
```


## 更多
   >   暂无
<!-- [Storybook - 基础元素 / 按钮 Button](./storybook/?selectedKind=基础元素 / 按钮 Button ":ignore") -->
