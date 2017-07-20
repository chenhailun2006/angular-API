# LowerCasePipe `PIPE`
**npm packages:** `@angular/common`

**Module:**
```javascript
import { LowerCasePipe } from '@angular/common';
```
#### 描述
将文本转换为小写形式。

#### 用法
`string_expression | lowercase`

#### 实例
```javascript
@Component({
  selector: 'lowerupper-pipe',
  template: `<div>
    <label>Name: </label><input #name (keyup)="change(name.value)" type="text">
    <p>In lowercase: <pre>'{{value | lowercase}}'</pre>
    <p>In uppercase: <pre>'{{value | uppercase}}'</pre>
  </div>`
})
export class LowerUpperPipeComponent {
  value: string;
  change(value: string) { this.value = value; }
}
```