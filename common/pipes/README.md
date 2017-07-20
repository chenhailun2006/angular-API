# 内置管道说明
Angular根据业务场景的需要，封装了一些常用的内置管道，内置管道可以直接在任何的模板表达式中使用，不需要通过`import`导入，也不需要在模块中声明。Angular提供的内置管道有：

[AsyncPipe](./asyncPipe.md)

[CurrencyPipe](./currencyPipe.md)

[DatePipe](./datePipe.md)

[DecimalPipe](./decimalPipe.md)

[JsonPipe](./jsonPipe.md)

[LowerCasePipe](./lowercasePipe.md)

[PercentPipe](./percentPipe.md)

[SlicePipe](./slicePipe.md)

[TitleCasePipe](./titlecasePipe.md)

[UpperCasePipe](./uppercasePipe.md)

## 自定义管道
虽然Angular提供了许多的内置管道，但是数据转换涉及各种各样的格式，内置管道无法满足所有的需求，因此有时需要我们自己使用Angular提供的自定义管道功能来实现更多的需求。要自定义管道，需要完成以下几步：

#### 1.定义元数据
通过@Pipe装饰器来定义一个管道类，该装饰器的元数据有一个name属性，使用此属性来指定管道的名称，这个名称必须是有效的Javascript标志符。

**注意：** 在使用@Pipe定义元数据前，必须导入Pipe
```javascript
import { Pipe } from '@angular/core';
```

#### 2.实现transform方法
自定义的管道类必须实现PipeTransform接口，并且需要实现PipeTransform接口的transform()方法。该方法的第一个参数为需要被转换的值，后面可以有若干个可选转换参数，该方法需要返回一个转换后的值。

#### 3.使用自定义管道
在组件的模板中使用自定义管道之前，必须在@NgModule的元数据declarations数组中添加自定义管道。添加到declarations数组中后，就可以像内置管道一样使用自定义管道了。