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
    //对象
    const obj={a:0,b:1};
    const {a,c=2}=obj;

    //数组
    const arr=['android','ios','react'];
    const [,,react,ionic='ionic'] = arr; //对于不需要的值留空（'android'，'ios'）
```
别名使用冒号(:)

```
    //对象
    const obj={a:0,b:1};
    const {a,b:otherName}=obj;

    // 数组（直接使用别名）
    const arr=['android','ios','react'];
    const [,apple,react] = arr;
    console.log(apple); //=>ios
```
别名与默认值一起使用

```
    //对象
    const obj={a:0,b:1};
    const {a,b:otherName=-1}=obj;

    //数组
    const arr=['android','ios','react'];
    const [,apple='macos',react,ionic='ionic'] = arr;
```

### 示例
#### 对象
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
#### 数组
```
const shop=['Coffee(hot)','$2.00','$2.50','$2.75'];

const [drink,,mediumCup,,superCup='$3.00'] = shop;

console.log(`A medium ${drink} costs ${mediumCup},A super ${drink} costs ${superCup}`);
```