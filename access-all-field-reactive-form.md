#Access to all form fields (Reactive form)

```typescript
import { Component } from '@angular/core';
import { AbstractControl, FormControl, FormGroup, FormArray, FormBuilder } from '@angular/forms';

@Component({
  selector: 'my-app',
  template: `
    <p>Count of dirty controls: {{ dirtyControls.length }}</p>
    <button (click)="markAsDirty(form)">Mark as dirty</button>
  `
})
export class AppComponent {

  form: AbstractControl;

  get dirtyControls(): AbstractControl[] {
    return flattenControls(this.form).filter(control => control.dirty);
  }

  constructor(private fb: FormBuilder) {
    this.form = fb.group({
      a: fb.control(''),
      b: fb.array([
        fb.control(''),
        fb.group({}),
        fb.array([])
      ])
    });
  }

  markAsDirty(form: AbstractControl): void {
    for (const control of flattenControls(this.form)) {
      control.markAsDirty({ onlySelf: true });
    }
  }
}

function flattenControls(form: AbstractControl): AbstractControl[] {
  let extracted: AbstractControl[] = [ form ];
  if (form instanceof FormArray || form instanceof FormGroup) {
    const children = Object.values(form.controls).map(flattenControls);
    extracted = extracted.concat(...children);
  }
  return extracted;
}
```

[Working Demo](https://stackblitz.com/edit/angular-rimpty)