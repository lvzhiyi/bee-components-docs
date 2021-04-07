# 选择器 DatePicker

## 如何使用

> 手机端DatePicker选择器

```jsx
const { DatePicker } = bee

class Test extends React.Component{
    constructor(props){
        super(props)
        this.state = {
            someShow:false,
            dayData:'',
            mouthData:'',
            selected:'2019年-10月-10日',
        }
    }

    colChange = (item,i)=>{
        console.log(item,i)
    }

    pickerOk(item){
        console.log(item)
        const selected = item.map((m,i)=>(m.item.text)).join();
        const de = item.map((m,i)=>(m.index));
        this.setState({someShow:false,selected,de})
    }

    render(){
        return(
            <div>
                <button className="primary-btn" onClick={()=>this.setState({someShow:true})}>{this.state.selected}</button>
                <DatePicker
                    mode="datetime"
                    show={this.state.someShow}
                    onCancel={()=>this.setState({someShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({someShow:false})}
                    colChange={(item,i)=>this.colChange(item,i)}
                    startYear={2000}
                    endYear={2050}
                    title={'选择时间'}
                    defaultSelected='2019年-10月-10日'
                />
            </div>
        )
    }
}

```


## API

### DatePicker

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| mode          | 日期选择的类型, 可以是日期date,时间time,日期+时间datetime,年year,月month | ``string``  | date |
| show        | 控制picker是否显示，                                      | ``boolean``  | ``null`` |
| onCancel    | 点击取消按钮触发的回调，                                    | ``function``  | ``null`` |
| onOk        | 点击确定按钮触发的回调`params: ([{item:选中的文案，i:选中的属于每列下标index, col:属于的列数index}])=>{}`，| ``function``  | ``null`` |
| onMaskClick  | 点击背景触发的回调，                                       | ``function``  | ``null`` |
| colChange        | picker改变时触发的回调，`params: ([当前选中的文案]=>{}` | ``function``  | ``null`` |
| startTime        | 开始时间        格式为   2019-10-10              | ``string``  | ``null`` |
| endTime        | 结束时间          格式为   2019-10-10             | ``string``  | ``null`` |
| title          | picker主题文案，                                       | ``string``  | ``null`` |
| defaultSelected    | 默认年限 格式为   2019年-10月-10日                   | ``string``  | ``null`` |
| hoursType     | 小时格式，默认24小时制                                     | ``string``  | 24 |



## 实例演示
### 默认date
```jsx
/*react*/
<script>
const { DatePicker } = bee

export default class Test extends React.Component{
    constructor(props){
        super(props)
        this.state = {
            someShow:false,
            selected:'选择时间',
        }
    }

    colChange = (item,i)=>{
        console.log(item,i)
    }

    pickerOk(item){
        console.log(item)
        const selected = item.map((m,i)=>(m.item.text)).join();
        const de = item.map((m,i)=>(m.index));
        this.setState({someShow:false,selected,de})
    }

    render(){
        return(
            <div>
                <button className="primary-btn" onClick={()=>this.setState({someShow:true})}>{this.state.selected}</button>
                <DatePicker
                    show={this.state.someShow}
                    onCancel={()=>this.setState({someShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    colChange={(item,i)=>this.colChange(item,i)}
                    title={'选择时间'}
                />
            </div>
        )
    }
}
</script>
```

### datetime
```jsx
/*react*/
<script>
const { DatePicker } = bee

export default class Test extends React.Component{
    constructor(props){
        super(props)
        this.state = {
            someShow:false,
            selected:'选择时间',
        }
    }

    colChange = (item,i)=>{
        console.log(item,i)
    }

    pickerOk(item){
        console.log(item)
        const selected = item.map((m,i)=>(m.item.text)).join();
        const de = item.map((m,i)=>(m.index));
        this.setState({someShow:false,selected,de})
    }

    render(){
        return(
            <div>
                <button className="primary-btn" onClick={()=>this.setState({someShow:true})}>{this.state.selected}</button>
                <DatePicker
                    mode="datetime"
                    show={this.state.someShow}
                    onCancel={()=>this.setState({someShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({someShow:false})}
                    colChange={(item,i)=>this.colChange(item,i)}
                />
            </div>
        )
    }
}
</script>
```

### defaultSelected
```jsx
/*react*/
<script>
const { DatePicker } = bee

export default class Test extends React.Component{
    constructor(props){
        super(props)
        this.state = {
            someShow:false,
            selected:'2019年-10月-10日',
        }
    }

    colChange = (item,i)=>{
        console.log(item,i)
    }

    pickerOk(item){
        console.log(item)
        const selected = item.map((m,i)=>(m.item.text)).join();
        const de = item.map((m,i)=>(m.index));
        this.setState({someShow:false,selected,de})
    }

    render(){
        return(
            <div>
                <button className="primary-btn" onClick={()=>this.setState({someShow:true})}>{this.state.selected}</button>
                <DatePicker
                    mode="datetime"
                    show={this.state.someShow}
                    onCancel={()=>this.setState({someShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({someShow:false})}
                    colChange={(item,i)=>this.colChange(item,i)}
                    startYear={2000}
                    endYear={2050}
                    title={'选择时间'}
                    defaultSelected='2019年-10月-10日'
                />
            </div>
        )
    }
}
</script>
```

### startTime and endTime
```jsx
/*react*/
<script>
const { DatePicker } = bee

export default class Test extends React.Component{
    constructor(props){
        super(props)
        this.state = {
            someShow:false,
            dayData:'',
            mouthData:'',
            selected:'2018年-9月-5日',
        }
    }

    colChange = (item,i)=>{
        console.log(item,i)
    }

    pickerOk(item){
        console.log(item)
        const selected = item.map((m,i)=>(m.item.text)).join();
        const de = item.map((m,i)=>(m.index));
        this.setState({someShow:false,selected,de})
    }

    render(){
        return(
            <div>
                <button className="primary-btn" onClick={()=>this.setState({someShow:true})}>{this.state.selected}</button>
                <DatePicker
                    mode="datetime"
                    show={this.state.someShow}
                    onCancel={()=>this.setState({someShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({someShow:false})}
                    colChange={(item,i)=>this.colChange(item,i)}
                    title={'选择时间'}
                    defaultSelected='2018年-9月-5日'
                    startTime={'2011-10-10'}
                    endTime={'2022-9-5'}
                />
            </div>
        )
    }
}
</script>
```
## 更多
> 暂无