# PercentPipe `PIPE`
**npm package:** `@angular/common`

**Module:**
```javascript
import { PercentPipe } from '@angular/common';
```
根据区域规则将一个数字格式化为百分比形式。

#### 用法
`number_expression | percent[:digitInfo]`

#### 描述
将一个数字转换为百分比形式。

`digitInfo`的详细信息请参阅[`DecimalPipe`](./decimalPipe.md)。

#### 实例
```javascript
@Component({
  selector: 'percent-pipe',
  template: `<div>
    <p>A: {{a | percent}}</p>
    <p>B: {{b | percent:'4.3-5'}}</p>
  </div>`
})
export class PercentPipeComponent {
  a: number = 0.259;
  b: number = 1.3495;
}
```
