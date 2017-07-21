# Component `DECORATOR`
标记一个类，使其作为Angular组件，并且收集组件的元数据配置信息。

#### 元数据概览
```javascript
@Component({ 
  changeDetection?: ChangeDetectionStrategy
  viewProviders?: Provider[]
  moduleId?: string
  templateUrl?: string
  template?: string
  styleUrls?: string[]
  styles?: string[]
  animations?: any[]
  encapsulation?: ViewEncapsulation
  interpolation?: [string, string]
  entryComponents?: Array<Type<any>|any[]>
})
```
#### 用法
```javascript
@Component({selector: 'greet', template: 'Hello {{name}}!'})
class Greet {
  name: string = 'World';
}
```
#### 描述
组件装饰器用来将一个类标记为Angular组件，并提供一些元数据来决定如何处理该组件，以及在运行时如何实例化和使用该组件。

在Angular应用中组件是最基本的UI构建块。Angular应用其实就是一个组件树。Angular组件是指令的一个子集。然而与指令不同的是，组件总是具有一个模板的，而且在一个模板中只能实例化一个组件。

要想让一个组件能够被其他组件或整个应用使用，它必须隶属于一个NgModule，而要想指定某个组件是某个NgModule的成员，就需要在NgModule的元数据`declarations`中列出。

除了在组件装饰器中指定元数据配置信息外，组件还可以通过实现各种各样的生命周期钩子来控制它的运行时行为。

#### 元数据属性
* **animations** 组件的动画列表

* **changeDetection** 组件所使用的变化检测策略

* **encapsulation** 组件使用的样式封装策略

* **entryComponents** 可以动态插入到此组件视图中的组件列表

* **exportAs** 组件实例在模板中导出的名称

* **host** 宿主元素绑定的事件、属性的类属性映射

* **inputs** 组件的输入属性列表

* **interpolation** 组件模板中使用的自定义插值标记

* **moduleId** 组件所属模块的模块ID

* **outputs** 组件的输出属性列表

* **providers** 组件及其子组件可以使用的提供者

* **queries** 配置可以注入到组件中的查询

* **selector** 用于在其他模板中识别此组件的CSS选择器

* **styleUrls** 应用于此组件的样式表文件列表

* **styles** 应用于此组件的行内样式列表

* **template** 此组件视图的内联模板

* **templateUrl** 此组件视图的模板文件

* **viewProviders** 此组件及其视图子元素可用的提供者

#### 实例
```javascript
@Component({selector: 'greet', template: 'Hello {{name}}!'})
class Greet {
  name: string = 'World';
}
```
##### 元数据属性
