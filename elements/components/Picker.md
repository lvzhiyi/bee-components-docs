# 选择器 Picker

## 如何使用

> 手机端picker选择器，支持单条选择与多条联动选择

```jsx
const { Picker } = bee

export default class App extends React.Component {
    constructor(props){
        super(props)
        this.state = {
            show:false
        }
    }

    colChange = (item,i,c)=>{
        console.log(item,i,c)
    }

    pickerOk(item){
        console.log(item)
        this.setState({show:false})
    }

    render() {
        return (
            <div>
                <button onClick={()=>this.setState({show:true})}>单条选择</button>
                <Picker
                    show={this.state.show}
                    onCancel={()=>this.setState({show:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({show:false})}
                    lang={{cancelBtn: 'cancel', okBtn: 'ok'}}
                    transparent={false}
                    title={'选择性别'}
                >
                    <Picker.PickerColumn
                        data={['男','女'].map((item,i)=>({text:item}))}
                        colChange={this.colChange}
                        columnIndex={0}
                        defaultIndex={0}
                    />
                </Picker>
            </div>
        );
    }
}

```


## API

### Picker

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| lang          | 取消与确认按钮的文案text，                              | ``Object``  | ``{ cancelBtn: '取消', okBtn: '确认' }`` |
| title        | piker的主题文案，                                      | ``string``  | ``请选择`` |
| transparent  | 是否启用遮罩背景，                                      | ``boolean``  | ``true`` |
| cascade     | 是否联动选择，                                      | ``boolean``  | ``false`` |
| show        | 控制picker是否显示的状态，                                  | ``boolean``  | ``false`` |
| onMaskClick  | 点击背景触发的回调，                                       | ``function``  | ``null`` |
| onCancel        | 点击取消按钮触发的回调，                                 | ``function``  | ``null`` |
| onOk        | 点击确定按钮触发的回调，`params: ([{item:选中的文案，i:选中的属于每列下标index, col:属于的列数index}])=>{}`| ``array``  | ``null`` |



### Picker.PickerColumn

|   属性         |                       说明                       |  类型   |   默认值    |
| ---------------| ------------------------------------------------ | ------- | ----------- |
| data         | 数据源，*数据的文案key值需要转换为‘text’*               | string  | ``null`` |
| colChange    | 选中每项后触发的回调，params: (item:选中的文案，i:选中的属于每列下标index, col:属于的列数index )=>{}| ``Object``  | ``null`` |
| defaultIndex  | 默认选中的index                                      | ``number``  | 0 |




## 实例演示
### 单条选择
```jsx
/*react*/
<script>
const { Picker } = bee

export default class App extends React.Component {
    constructor(props){
        super(props)
        this.state = {
            show:false,
            selected:'男'
        }
    }

    colChange = (item,i,c)=>{
        console.log(item,i,c)
    }

    pickerOk(item){
        console.log(item)
        this.setState({show:false,selected:item[0].item.text})
    }

    render() {
        return (
            <div>
                <button className="primary-btn" onClick={()=>this.setState({show:true})}>{this.state.selected}</button>
                <Picker
                    show={this.state.show}
                    onCancel={()=>this.setState({show:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({show:false})}
                    lang={{cancelBtn: 'cancel', okBtn: 'ok'}}
                    transparent={false}
                    title={'选择性别'}
                >
                    <Picker.PickerColumn
                        data={['男','女'].map((item,i)=>({text:item}))}
                        colChange={this.colChange}
                        columnIndex={0}
                        defaultIndex={0}
                    />
                </Picker>
            </div>
        );
    }
}
</script>
```

### 多条选择

```jsx
/*react*/
<script>
const { Picker } = bee

const mouthDatas = ['一月','二月','三月'];
const dayDatas = ['一号','二号','三号','四号','五号','六号','七号','八号','九号','十号','十一号','十二号',]


export default class Test extends React.Component {
    constructor(props){
        super(props)
        this.initData = this.initData.bind(this);
        this.state = {
            someShow:false,
            dayData:'',
            mouthData:'',
            selected:'二月,四号',
            de:[1,3]
        }
    }

    initData(){
        const mouthData = mouthDatas.map((item,i)=>({text:item}));
        const dayData = dayDatas.map((item,i)=>({text:item}));
        this.setState({dayData,mouthData})
    }

    componentWillMount(){
        this.initData();
    }

    colChange = (item,i)=>{
        console.log(item)
    }

    pickerOk(item){
        console.log(item)
        const selected = item.map((m,i)=>(m.item.text)).join();
        const de = item.map((m,i)=>(m.index));
        this.setState({someShow:false,selected,de})
    }

    render() {
        const { dayData,mouthData,de } = this.state;
        return (
            <div>
                <button className="primary-btn" onClick={()=>this.setState({someShow:true})}>{this.state.selected}</button>
                <Picker
                    show={this.state.someShow}
                    onCancel={()=>this.setState({someShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({someShow:false})}
                    title={'选择时间'}

                >
                    <Picker.PickerColumn
                        data={mouthData}
                        colChange={this.colChange}
                        defaultIndex={de[0]}
                    />
                    <Picker.PickerColumn
                        data={dayData}
                        defaultIndex={de[1]}
                    />
                </Picker>
            </div>
        );
    }
}
</script>
```


### 城市联动选择
```jsx
/*react*/
<script>
const { Picker,cityDatas } = bee
console.log(bee)

export default class App extends React.Component{
    constructor(props){
        super(props)
        this.initData = this.initData.bind(this);
        this.state = {
            cityShow:false,
            prvData:'',
            cityData:'',
            strData:'',
            selected:'香港特别行政区,九龙,黄大仙区',
            selectedIndex:[4,0,1],
        }
    }

    initData(){
        const de = this.state.selectedIndex;
        const prvData = cityDatas;
        const cityData = cityDatas[de[0]].children
        const strData = cityData[de[1]].children
        this.setState({prvData,cityData,strData})
    }

    componentWillMount(){
        this.initData();
    }

    cityChange = (item,i)=>{
        if(item.children[0].children.length > 0){
            const cityData = item.children;
            const strData = cityData[0].children;
            this.setState({cityData,strData})
        }else{
            const strData = item.children;
            this.setState({strData})
        }
    }

    pickerOk(item){
        const selected = item.map((m,i)=>(m.item.text)).join();
        const selectedIndex = item.map((m,i)=>(m.index));
        console.log(selected,selectedIndex)
        this.setState({cityShow:false,selected,selectedIndex})
    }

    render() {
        const { prvData,cityData,strData } = this.state;
        const de = this.state.selectedIndex
        return (
            <div>
                <button className="primary-btn" onClick={()=>{this.initData();this.setState({cityShow:true})}}>{this.state.selected}</button>
                <Picker
                    show={this.state.cityShow}
                    onCancel={()=>this.setState({cityShow:false})}
                    onOk={(item)=>this.pickerOk(item)}
                    onMaskClick={()=>this.setState({cityShow:false})}
                    cascade={true}
                >
                    <Picker.PickerColumn
                        data={prvData}
                        colChange={this.cityChange}
                        defaultIndex={de[0]}
                    />
                    <Picker.PickerColumn
                        data={cityData}
                        colChange={this.cityChange}
                        defaultIndex={de[1]}
                    />
                    <Picker.PickerColumn
                        data={strData}
                        defaultIndex={de[2]}
                    />
                </Picker>
            </div>
        );
    }
}
</script>
```
## 更多
> 暂无