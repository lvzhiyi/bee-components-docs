# 日历 Calendar

## 如何使用


```jsx
import { Calendar } from 'bee'

class Test extends Component {
    constructor(props:any){
        super(props)
        this.state = {
            show:false,
            date:'选择日期',
            defaultDate:''
        }
    }
    onDayClick =(day:any)=>{
        console.log(day)
    }
    onOk(date:any){
        console.log(date)
        this.setState({show:false,date,defaultDate:date})
    }
    chooiceDate = ()=>{
        this.setState({show:true})
    }
    render() {
        const {date,show,defaultDate} = this.state;
        return (
            <div className="container">
                <button className="primary-btn" onClick={this.chooiceDate}>{date}</button>
                <Calendar
                    todayAsBefore={true}
                    onDayClick={(day:any)=> this.onDayClick(day)}
                    lang={{'cancelBtn': 'cancel', 'okBtn': 'ok'}}
                    title="选择日期"
                    onOk={(date:any)=>this.onOk(date)}
                    onCancel={()=>this.setState({show:false})}
                    show={show}
                    defaultSelectDay={defaultDate}
                />
            </div>
        );
    }
}

```
## API
## Calendar

|   属性         |                       说明                          |  类型   |   默认值    |
| ---------------| -------------------------------------------------  | ------- | ----------- |
| defaultSelectDay  | 默认选中哪一天，格式：2018-05-29                    | string  | 当天        |
| onDayClick    | 点击日期的回调      ``(params:value)=>{}``             | function  | ``null`` |
| onNextMonth   | 点击下一月的回调     ``(params:value)=>{}``             | function  | ``null`` |
| onPreMonth    | 点击下一月的回调     ``(params:value)=>{}``              | function  | ``null`` |
| onNextYear   | 点击下一年的回调     ``(params:value)=>{}``             | function  | ``null`` |
| onPreYear    | 点击下一年的回调     ``(params:value)=>{}``              | function  | ``null`` |
| weekShort     | 周名称排序，为`true`时已周一开始，`false`已周日开始      | Boolean  | ``false`` |
| disableDay   | 禁用的日期 ，格式：2018-05-29                            | string  | ``null`` |
| disableFlip   | 为`true`时，只有禁用可点击 , 其他不可点击                           | Boolean  | ``false`` |
| todayAsBefore |为`true`时，已当前日期为准，之前的日期不可选               | Boolean  | ``true`` |
| onOk          | 点击确定按钮时的回调 ``(params:value)=>{}``              | function  | ``null`` |
| onCancel      | 点击取消按钮时的回调 ``()=>{}``                         | function  | ``null`` |
| lang          | 确定取消按钮的文本，格式 ``{ cancelBtn: '取消', okBtn: '确认' }``| Ojbect  | ``{ cancelBtn: '取消', okBtn: '确认' }`` |
| title         | 主题文本                                               | string  | ``请选择`` |




## 实例演示
```jsx
/*react*/
<script>
const { Calendar } = bee

export default class App extends React.Component {
    constructor(props:any){
        super(props)
        this.state = {
            show:false,
            date:'选择日期',
            defaultDate:''
        }
    }
    onDayClick =(day:any)=>{
        console.log(day)
    }
    onOk(date:any){
        console.log(date)
        this.setState({show:false,date,defaultDate:date})
    }
    chooiceDate = ()=>{
        this.setState({show:true})
    }
    render() {
        const {date,show,defaultDate} = this.state;
        return (

            <div className="container">
                <button className="primary-btn" onClick={this.chooiceDate}>{date}</button>
                <Calendar
                    onDayClick={(day:any)=> this.onDayClick(day)}
                    lang={{'cancelBtn': 'cancel', 'okBtn': 'ok'}}
                    title="选择日期"
                    onOk={(date:any)=>this.onOk(date)}
                    onCancel={()=>this.setState({show:false})}
                    show={show}
                    defaultSelectDay={defaultDate}
                />
            </div>
        );
    }
}
</script>
```

#### disableDay
```jsx
/*react*/
<script>
const { Calendar } = bee

export default class App extends React.Component {
    constructor(props:any){
        super(props)
        this.state = {
            show:false,
            date:'选择日期',
            defaultDate:''
        }
    }
    onDayClick =(day:any)=>{
        console.log(day)
    }
    onOk(date:any){
        console.log(date)
        this.setState({show:false,date,defaultDate:date})
    }
    chooiceDate = ()=>{
        this.setState({show:true})
    }
    render() {
        const {date,show,defaultDate} = this.state;
        return (

            <div className="container">
                <button className="primary-btn" onClick={this.chooiceDate}>{date}</button>
                <Calendar
                    todayAsBefore={false}
                    onDayClick={(day:any)=> this.onDayClick(day)}
                    disableDay={['2018-05-20','2018-05-21']}
                    onOk={(date:any)=>this.onOk(date)}
                    onCancel={()=>this.setState({show:false})}
                    show={show}
                    defaultSelectDay={defaultDate}
                />
            </div>
        );
    }
}
</script>
```

#### disableFlip
```jsx
/*react*/
<script>
const { Calendar } = bee

export default class App extends React.Component {
    constructor(props:any){
        super(props)
        this.state = {
            show:false,
            date:'选择日期',
            defaultDate:''
        }
    }
    onDayClick =(day:any)=>{
        console.log(day)
    }
    onOk(date:any){
        console.log(date)
        this.setState({show:false,date,defaultDate:date})
    }
    chooiceDate = ()=>{
        this.setState({show:true})
    }
    render() {
        const {date,show,defaultDate} = this.state;
        return (

            <div className="container">
                <button className="primary-btn" onClick={this.chooiceDate}>{date}</button>
                <Calendar
                    disableFlip={true}
                    todayAsBefore={false}
                    onDayClick={(day:any)=> this.onDayClick(day)}
                    disableDay={['2018-05-20','2018-05-21']}
                    onOk={(date:any)=>this.onOk(date)}
                    onCancel={()=>this.setState({show:false})}
                    show={show}
                    defaultSelectDay={defaultDate}
                />
            </div>
        );
    }
}
</script>
```

## 更多
> 暂无