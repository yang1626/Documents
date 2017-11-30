##  组件的默认状态（defaultState）

### 基本类型组件：

```
class MyComponent extends React.Component {
    constructor(props){
        super(props);
        this.state={
            name:props.name
        };
    }
}

MyComponent.defaultProps={
    name:'default name'
};

```

### 功能型组件

```
const MyFunctionalComponent=(props)=>{
    return (
        <div>
            <p>{props.name}</p>
        </div>
    );
}

MyFunctionalComponent.defaultProps={
    name:'default name'
};

```