# DatePipe `PIPE`
**npm packages:** `@angular/common`

**Modules:**
```javascript
import { DatePipe } from '@angular/common';
```
根据区域规则格式化日期。

#### 用法
`date_expression | date[:format]`

#### 描述
其中：

  * `date_expression`是一个日期对象，或者是一个数字（时间戳），也可以是[ISO字符串](https://www.w3.org/TR/NOTE-datetime)
  
  * `format`用于指定在对日期进行格式化时所使用的格式，可以是如下的格式：
  
    * `'medium'`：等价于`'yMMMdjms'`，例如Sep 3, 2010, 12:05:08 PM
    
    * `'short'`：等价于`'yMdjm'`，例如9/3/2010, 12:05 PM
    
    * `'fullDate'`：等价于`'yMMMMEEEEd'`，例如Friday, September 3, 2010
    