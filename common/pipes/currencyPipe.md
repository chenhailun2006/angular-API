# CurrencyPipe `PIPE`
**nmp package:** `@angular/common`

**Module:**
```javascript
import { CurrencyPipe } from '@angular/common';
```
使用区域规则将一个数字格式化为货币字符串形式。

#### 用法
`number_expression | currency[:currencyCode[:symbolDisplay[:digitInfo]]]`

#### 描述
使用`currency`将一个数字格式化为货币字符串形式。其中：

* `currencyCode`是[ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)货币代码，例如美元为`USD`，欧元为`EUR`

* `symbolDisplay`是一个布尔值，用来决定是使用货币符号还是使用货币代码：

    `true`使用货币符号（比如¥，$）
    
    `false`使用货币代码，比如USD，CNY，EUR

* `digitInfo`请参阅`DecimalPipe`了解详细信息

#### 实例
```javascript
@Component({
  selector: 'currency-pipe',
  template: `<div>
    <p>A: {{a | currency:'USD':false}}</p>
    <p>B: {{b | currency:'USD':true:'4.2-2'}}</p>
  </div>`
})
export class CurrencyPipeComponent {
  a: number = 0.259;
  b: number = 1.3495;
}
```