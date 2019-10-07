# Custom Preloading

```typescript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule, ModuleWithProviders } from '@angular/core';
import { PreloadingStrategy, Route, Routes, RouterModule } from '@angular/router';
import { Observable, of } from 'rxjs';
import { AppComponent } from './app.component';

function preloadingConnection(): boolean {
  const connection = navigator['connection'];
  if (connection) {
    const effectiveType = connection.effectiveType || '';
    if (connection.saveData || effectiveType.includes('2g')) {
      return false;
    }
  }
  return true;
}

class CustomPreloading implements PreloadingStrategy {
  public preload(route: Route, load: () => Observable<any>): Observable<any> {
    return  preloadingConnection() ? load() : of(null);
  }
}

const routes: Routes = [
  {
      path: '',
      redirectTo: 'items',
      pathMatch: 'full'
  },
  {
      path: 'items',
      loadChildren: 'app/items/items.module#ItemsModule'
  },
  {
      path: 'item',
      loadChildren: 'app/details/details.module#DetailsModule'
  }
];

const routing: ModuleWithProviders = RouterModule.forRoot(routes, {
  preloadingStrategy: CustomPreloading
});

@NgModule({
  imports: [routing],
  exports: [RouterModule],
  providers: [CustomPreloading]
})
class RoutingModule {}

@NgModule({
  imports: [BrowserModule, RoutingModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}

```