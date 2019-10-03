
# Binding Specific Keys to the Keyup and Keydown Events

When binding to either the keyup or keydown events in your Angular 2+ templates, you can specify key names. This makes it very easy to trigger the event only when specific keys are pressed.


```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  template: `
    <h2>Type something in the input and hit control+enter to
        update the value below:</h2>

    <h1>{{value || 'no value'}}</h1>
    <input (keydown.control.enter)="value=$event.target.value; $event.target.value = ''">
  `
})
export class AppComponent {
    value: string;
}
```

## Examples

```typescript
<input (keydown.enter)="...">
<input (keydown.a)="...">
<input (keydown.esc)="...">
<input (keydown.shift.esc)="...">
<input (keydown.control)="...">
<input (keydown.alt)="...">
<input (keydown.meta)="...">
<input (keydown.9)="...">
<input (keydown.tab)="...">
<input (keydown.backspace)="...">
<input (keydown.arrowup)="...">
<input (keydown.shift.arrowdown)="...">
<input (keydown.shift.control.z)="...">
<input (keydown.f4)="...">

```




[Working Demo](https://stackblitz.com/edit/angular-x3nleg),
[link](https://alligator.io/angular/binding-keyup-keydown-events)