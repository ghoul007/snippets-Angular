# Observable as output

```typescript

import { Component, Output } from '@angular/core';
import { FormControl } from '@angular/forms';

@Component({
  selector: 'my-child',
  template: `<input type=checkbox [formControl]="control">`
})
export class ChildComponent {
  readonly control = new FormControl();
  @Output() valueChange = this.control.valueChanges
}

@Component({
  selector: 'my-app',
  template: `
  <h1>{{value}}</h1>
  <my-child (valueChange)="value = $event"></my-child> `
})
export class AppComponent {
  value = 'Check or uncheck';
}
```
