# injecting document

```typescript

import { Component } from '@angular/core';
import { DOCUMENT } from '@angular/common';
import { Inject } from '@angular/core';

@Component({
  selector: 'my-app',
  template: `<h1>Edit me </h1>`
})
export class AppComponent {
  constructor(@Inject(DOCUMENT) private document: Document) {
    // Don't do this in prod!
    document.body.style.backgroundColor = 'pink';
  }
}

```
