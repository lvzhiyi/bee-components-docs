# 手风琴 Accordion

## 如何使用
```jsx
import { Accordion } from 'bee-react'

export default class App extends React.Component {
  headClick(index, status){
      console.log(index, status)
  }
  render () {
    return <Accordion
                accordion={true}
                onChange={(index, status) =>
                    this.headClick(index, status)
                }
            >
                <Accordion.Panel key={1} head={() => (<div>head1</div>)}>
                    <ul>
                        <li>list1</li>
                        <li>list2</li>
                        <li>list3</li>
                    </ul>
                </Accordion.Panel>

            </Accordion>
  }
}
```


## API
## Accordion
|   属性   |                       说明                         |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
| accordion | 是否是手风琴模式，                                              | boolean  | false |
| defaultKey | 默认展开的key值，                                              | string  | ``null``  |
| onChange | 点击展开和关闭的回调    参数``(index:对应的key值，status:对应的状态)``| Funtion | ``null`` |

## Accordion.Panel
|   属性   |                       说明                       |  类型   |   默认值    |
| -------- | ------------------------------------------------ | ------- | ----------- |
| head | 头部内容，可选值为一个字符串或者 HtmlElement              | string or Fn  | ``null`` |
| className | 自定义class                                      | string  | ``null`` |


## 实例演示
```jsx
/*react*/
<script>
const { Accordion } = bee
export default class App extends React.Component {
  headClick(index, status){
      console.log(index, status)
  }
  render () {
    return<div>
            <h2>手风琴</h2>
            <Accordion
                accordion={true}
                onChange={(index, status) =>
                    this.headClick(index, status)
                }
            >
                <Accordion.Panel key={1} head={() => (<div className="primary-btn">head1</div>)}>
                    <ul>
                        <li>list1</li>
                        <li>list2</li>
                        <li>list3</li>
                    </ul>
                </Accordion.Panel>
                <Accordion.Panel key={2} head={() => (<div className="primary-btn">head2</div>)}>
                    <ul>
                        <li>list1</li>
                        <li>list2</li>
                        <li>list3</li>
                    </ul>
                </Accordion.Panel>
            </Accordion>
            <h2>非手风琴</h2>
            <Accordion
                accordion={false}
                onChange={(index, status) =>
                    this.headClick(index, status)
                }
            >
                <Accordion.Panel key={1} head={() => (<div className="primary-btn">head1</div>)}>
                    <ul>
                        <li>list1</li>
                        <li>list2</li>
                        <li>list3</li>
                    </ul>
                </Accordion.Panel>
                <Accordion.Panel key={2} head={() => (<div className="primary-btn">head2</div>)}>
                    <ul>
                        <li>list1</li>
                        <li>list2</li>
                        <li>list3</li>
                    </ul>
                </Accordion.Panel>
            </Accordion>
        </div>
    }
}
</script>
```


## 更多
   >   暂无
<!-- [Storybook - 基础元素 / 按钮 Button](./storybook/?selectedKind=基础元素 / 按钮 Button ":ignore") -->
