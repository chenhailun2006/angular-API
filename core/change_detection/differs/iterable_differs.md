# IterableDiffers `Class`
**npm packages:**  `@angular/core`

**Module:** 
```javascript
import { IterableDiffers } from @angular/core;
```

### 预览
```javascript
class IterableDiffers {
  static create(factories: IterableDifferFactory[], parent?: IterableDiffers): IterableDiffers
  static extend(factories: IterableDifferFactory[]): Provider
  factories: IterableDifferFactory[]
  find(iterable: any): IterableDifferFactory
}
```
### 描述
它是一个仓库，用来存放各种不同的迭代变化检测策略，这些策略能够被NgFor, NgClass等指令所使用。

### 静态成员
```javascript
static create(factories: IterableDifferFactory[], parent?: IterableDiffers): IterableDiffers
```
根据指定的迭代变化检测策略工厂创建一个新的`IterableDiffers`对象。如果存在parent参数，则将parent中的`IterableDifferFactory`数组拼接到指定的factories后，再创建一个新的`IterableDiffers`对象。该函数的定义如下：
```javascript
static create(factories: IterableDifferFactory[], parent?: IterableDiffers): IterableDiffers {
  if (parent != null) {
    const copied = parent.factories.slice();
    factories = factories.concat(copied);
    return new IterableDiffers(factories);
  } else {
    return new IterableDiffers(factories);
  }
}
```
***
```javascript
static extend(factories: IterableDifferFactory[]): Provider
```
此函数接收一个`IterableDifferFactory`数组，然后返回一个继承自`IterableDiffers`实例的提供者，返回的提供者携带了一个工厂方法`useFactory`，该方法可以返回一个新的`IterableDiffers`实例。该函数的定义如下：
```javascript
static extend(factories: IterableDifferFactory[]): Provider {
  return {
    provide: IterableDiffers,
    useFactory: (parent: IterableDiffers) => {
      if (!parent) {
        throw new Error('Cannot extend IterableDiffers without a parent injector');
      }
      return IterableDiffers.create(factories, parent);
    },
    deps: [[IterableDiffers, new SkipSelf(), new Optional()]]
  };
}
```
### 构造函数
```javascript
constructor(factories: IterableDifferFactory[]){ }
```
### 实例成员
```javascript
factories: IterableDifferFactory[]
```
返回该`IterableDiffers`对象的`IterableDifferFactory`数组。

```javascript
find(iterable: any): IterableDifferFactory
```
根据指定的iterable参数，在当前`IterableDiffers`对象的`IterableDifferFactory`数组中查找支持该iterable的`IterableDifferFactory`。如果找不到则会抛出错误。该函数的定义如下：
```javascript
find(iterable: any): IterableDifferFactory {
  const factory = this.factories.find(f => f.supports(iterable));
  if (factory != null) {
    return factory;
  } else {
    throw new Error(
        `Cannot find a differ supporting object '${iterable}' of type '${getTypeNameForDebugging(iterable)}'`);
  }
}
```
