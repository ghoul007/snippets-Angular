# Access Enum in template

Pass enums in angular view templates

```typescript

import { Component } from "@angular/core";

enum Animals {
  DOG,
  CAT,
  DOLPHIN
}

@Component({
  selector: "my-app",
  template: `<div *ngIf="value === animalsEnum.CAT">meow</div>`,
})
export class AppComponent {
  value: Animals = Animals.CAT;
  animalsEnum : typeof Animals = Animals;
}
```

[Working Demo](https://stackblitz.com/edit/angular-dkvisr)