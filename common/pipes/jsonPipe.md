# JsonPipe `PIPE`
**npm Package:** `@angular/common`

**Module：** 
```javascript
import { JsonPipe } from '@angular/common';
```
#### 用法
`expression | json`

#### 描述
使用`JSON.stringify`方法将给定表达式的值转换为字符串形式。在调试时很有用。

#### 实例
```javascript
@Component({
  selector: 'json-pipe',
  template: `<div>
    <p>Without JSON pipe:</p>
    <pre>{{object}}</pre>
    <p>With JSON pipe:</p>
    <pre>{{object | json}}</pre>
  </div>`
})
export class JsonPipeComponent {
  object: Object = {foo: 'bar', baz: 'qux', nested: {xyz: 3, numbers: [1, 2, 3, 4, 5]}};
}
```