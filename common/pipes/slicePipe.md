# SlicePipe `PIPE`
**npm package:** `@angular/common`

**Module:**
```javascript
import { SlicePipe } from '@angular/common';
```
用于裁剪数组或者字符串，并返回裁剪后的目标子集。

#### 用法
`array_or_string_expression | slice:start[:end]`

#### 描述
输入的表达式是一个数组或者是一个字符串。其中：

* `start`要返回的子集在原始数据中的开始索引
  
  * **是一个整数** 从`start`索引开始，返回其后所有的子集
  
  * **是一个负数** 从原始值的最后向前数到第`start`个索引开始，返回该索引之后的所有子集
  
  * **一个大于原始值长度的整数** 返回一个空集或空字符串
  
  * **一个绝对值大于原始值长度的负整数** 返回一个空集或空字符串
  
* `end`要返回的子集在原始数据中的结束索引
  
  * **省略** 返回从`start`索引开始及其之后的所有条目
  
  * **是一个整数** 返回从`start`索引开始到`end`索引结束（不包含`end`索引处的值）之间的子集
  
  * **是一个负数** 返回从`start`索引开始到`end`索引结束（注意：`end`索引从后向前数，并且不包含`end`索引处的值）之间的子集
  
#### 数组实例
```javascript
@Component({
  selector: 'slice-list-pipe',
  template: `<ul>
    <li *ngFor="let i of collection | slice:1:3">{{i}}</li>
  </ul>`
})
export class SlicePipeListComponent {
  collection: string[] = ['a', 'b', 'c', 'd'];
}
```

#### 字符串实例
```javascript
@Component({
  selector: 'slice-string-pipe',
  template: `<div>
    <p>{{str}}[0:4]: '{{str | slice:0:4}}' - output is expected to be 'abcd'</p>
    <p>{{str}}[4:0]: '{{str | slice:4:0}}' - output is expected to be ''</p>
    <p>{{str}}[-4]: '{{str | slice:-4}}' - output is expected to be 'ghij'</p>
    <p>{{str}}[-4:-2]: '{{str | slice:-4:-2}}' - output is expected to be 'gh'</p>
    <p>{{str}}[-100]: '{{str | slice:-100}}' - output is expected to be 'abcdefghij'</p>
    <p>{{str}}[100]: '{{str | slice:100}}' - output is expected to be ''</p>
  </div>`
})
export class SlicePipeStringComponent {
  str: string = 'abcdefghij';
}
```
  