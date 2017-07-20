# AsyncPipe `PIPE`
**npm packages:** `@angular/common`

**Module:**
```javascript
import { AsyncPipe } from '@angular/common';
```
获取异步类型的原始值。

#### 用法
`observable_or_promise_expression | async`

#### 描述
`async`异步管道可以订阅一个`Obsevable`或`Promise`并返回其发布的最新值。当一个新值发布时，`async`异步管道会标记组件，使其检测数据的变化。当组件被销毁时，`async`异步管道会自动取消订阅，从而避免潜在的内存泄漏问题。

#### 实例
下面实例将一个`Promise`绑定到了视图。点击`Resolve`按钮将会解析此承诺。
```javascript
@Component({
  selector: 'async-promise-pipe',
  template: `<div>
    <code>promise|async</code>: 
    <button (click)="clicked()">{{ arrived ? 'Reset' : 'Resolve' }}</button>
    <span>Wait for it... {{ greeting | async }}</span>
  </div>`
})
export class AsyncPromisePipeComponent {
  greeting: Promise<string>|null = null;
  arrived: boolean = false;

  private resolve: Function|null = null;

  constructor() { this.reset(); }

  reset() {
    this.arrived = false;
    this.greeting = new Promise<string>((resolve, reject) => { this.resolve = resolve; });
  }

  clicked() {
    if (this.arrived) {
      this.reset();
    } else {
      this.resolve!('hi there!');
      this.arrived = true;
    }
  }
}
```
也可以对`Observable`使用`async`。下面实例将一个`Observable`绑定到了视图。该`Observable`会随时间变化而持续更新视图。
```javascript
@Component({
  selector: 'async-observable-pipe',
  template: '<div><code>observable|async</code>: Time: {{ time | async }}</div>'
})
export class AsyncObservablePipeComponent {
  time = new Observable<string>((observer: Subscriber<string>) => {
    setInterval(() => observer.next(new Date().toString()), 1000);
  });
}
```