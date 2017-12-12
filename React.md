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