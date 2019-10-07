# Window Location InjectionToken

## how to inject window.location in angular project

```typescript
import { Component, Inject } from '@angular/core';
import { LOCATION_TOKEN } from './app.module';

@Component({
  selector: 'my-app',
  template: `{{ location.href }}`
})
export class AppComponent {
  constructor(
    @Inject(LOCATION_TOKEN) public location: Location
  ) {}

  useIt() {
    this.location.assign('xxx');
  }
}
```


```typescript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule, InjectionToken } from '@angular/core';
import { AppComponent } from './app.component';

export const LOCATION_TOKEN = new InjectionToken<Location>('Window location object');

@NgModule({
  imports: [BrowserModule],
  declarations: [AppComponent],
  providers: [
    { provide: LOCATION_TOKEN, useValue: window.location }
  ],
  bootstrap: [AppComponent]
})
export class AppModule {}

```