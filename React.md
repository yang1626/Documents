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

## import\export

### export
#### util.js
```
 // 具名export
 const mutil=x=>x*x;

 export {mutil};

 export const add = (a,b)=>a+b; //行内

 // 默认export

 const minus =(a,b) => a-b;
  1. export default minus; 
  2. export {mutil ,minus as default}
  3. export default (a,b)=> a-b;
  4. export default class Header extends React.Component {}
 ```
### import
```
import {mutil} from './util.js'

import defaultModule from './util.js' // defaultModule 为util.js默认export ，名称随意

import anyName,{mutil} from './util.js'

```

## ES6 解构赋值（Destructuring）
从数组和对象中按需提取属性值，对变量进行赋值，称为解构(destructuring)，适用于对象和数组。

### 默认值和别名
默认值用等号赋值
```
    const obj={a:0,b:1};
    const {a,c=2}=obj;

```
别名使用冒号(:)

```
    const obj={a:0,b:1};
    const {a,b:otherName}=obj;
```
别名与默认值一起使用

```
    const obj={a:0,b:1};
    const {a,b:otherName=-1}=obj;
```

### 示例
```
const person={
    name:'匿名',
    age:18,
    location:{
        city:'Beijing',
        // temp:-10
    }
};

const {name,age} = person;

console.log(`I'm ${name},${age}`);

const {city,temp:temperature=-100} =person.location;

console.log(`I'm in ${city},${temperature}℃`);
```
