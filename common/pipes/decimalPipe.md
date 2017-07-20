# DecimalPipe `PIPE`
**npm package:** `@angular/common`

**Module:**
```javascript
import { DecimalPipe } from '@angular/common';
```
根据区域规则格式化一个数字。

#### 用法
`number_expression | number[:digitInfo]`

将一个数字格式化为文本形式。其中：

* `number_expression`是一个数字

* `digitInfo`是一个字符串，具有如下的格式：

`{minIntegerDigits}.{minFractionDigits}-{maxFractionDigits}`
  * `minIntegerDigits`表示要使用的整数位数的最小数目
  
  * `minFractionDigits`表示要使用的小数位数的最小数目
  
  * `maxFractionDigits`表示要使用的小数位数的最大数目
  
#### 实例
```javascript
@Component({
  selector: 'number-pipe',
  template: `<div>
    <p>e (no formatting): {{e}}</p>
    <p>e (3.1-5): {{e | number:'3.1-5'}}</p>
    <p>pi (no formatting): {{pi}}</p>
    <p>pi (3.5-5): {{pi | number:'3.5-5'}}</p>
  </div>`
})
export class NumberPipeComponent {
  pi: number = 3.141592;
  e: number = 2.718281828459045;
}
```

