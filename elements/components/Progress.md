# 圆形进度条 Progress

## 如何使用

> 主要用于各种圆形进度条、环形图、饼状图

```jsx
import { Progress } from 'bee'

class App extends React.Component {
  render () {
    return <div>
              <Progress>100%</Progress>
           </div>
  }
}

```


## API
## data 接收一个数组对象，形成单个或多个圆形

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| width     | 圆形厚度，                                         | number  | ``65`` |
| value  | 进度值                                                   | number  | ``100`` |
| r    | 圆形半径                                                 | number  | ``160`` |
| color  | 接收一个字符串或者一个数组颜色作为渐变色              | array or string  | ``['#3AB078', '#000']`` |

## 其他API

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| centerTextClass | 中心文本自定class，                                | string  | ``null`` |
| children  | 自定义其他中心文本                                      | ReactElement  | ``null`` |


## 实例演示
### 单圈
```jsx
/*react*/
<script>

const { Progress } = bee

export default class App extends React.Component {
    render() {
        return (
            <div>
                <Progress>100%</Progress>
                <Progress
                    data={[
                        {
                            width:80,
                            value: 75,
                            color: ['#0f0','red'],
                            r: 100,
                            type:'circle'
                        }
                    ]}
                >75%</Progress>
            </div>

        );
    }
}
</script>
```

### 多圈

```jsx
/*react*/
<script>
const { Progress } = bee

export default class App extends React.Component {
    state = {
        data2:[]
    }

    componentDidMount(){
        setInterval(()=>{
            const data2 = 's'.repeat(10).split('').map((item,i) => {
                return {
                     width:120,
                     value: i%2 ==0 ? Math.floor(Math.random() * 100) : 100,
                     color: ['#' + Math.floor( Math.random() * 16777215 ).toString( 16 ),'#' + Math.floor( Math.random() * 16777215 ).toString( 16 )],
                     r: (165 + i * 50),
                     type:'circle'
                 }
             });
             this.setState({data2})
        },1000)
    }
    render() {
        const data1 = [
            {
                width:120,
                value: 75,
                color: ['#00FFE3','#271FD6'],
                r: 165,
                type:'circle'
            },
            {
                width:20,
                value: 100,
                color: ['#00FFE3','#271FD6'],
                r: 190,
                type:'circle'
            },
            {
                width:30,
                value: 100,
                color: 'grey',
                r: 230,
                type:'circle'
            }
        ];
        return (
            <div>
                <Progress data={data1}>75%</Progress>
                {
                    this.state.data2.length && <Progress data={this.state.data2}></Progress>
                }

            </div>

        );
    }
}
</script>
```


## 更多
> 暂无