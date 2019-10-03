#Use @HostBinding decorators

```typescript
  import { Component, HostBinding } from '@angular/core';

@Component({
   selector: 'my-app',
   template: `
    <div>Use the input below  to select host background-color:</div>
    <input type="color" [(ngModel)]="color">
  `,
  styles: [
    `:host { display: block; height: 100px; }`
  ]
})
export class AppComponent {
  @HostBinding('style.background') color = '#ff9900';
}
```

## examples

```typescript
  @HostBinding('style.align-items') alignItems = 'center';
  @HostBinding('style.justify-content') justifyContent = 'center';
  @HostBinding('style.vertical-align') verticalAlign = 'middle';
  @HostBinding('style.height') height = '100vh';
  @HostBinding('style.max-width') maxWidth = '100%';
  @HostBinding('style.width') width = '100%';
  @HostBinding('style.position') position = 'fixed';
  @HostBinding('style.z-index') zIndex = '99999';
  @HostBinding('style.background') background = 'rgba(0, 0, 0, .6)';
  @HostBinding('style.left') left = '0';
  @HostBinding('style.top') top = '0';
  @HostBinding('style.bottom') bottom = '0';
  @HostBinding('style.right') right = '0';
  @HostBinding('style.display') display = 'flex';

  ```

[Working Demo](https://stackblitz.com/edit/angular-bg3xqs)