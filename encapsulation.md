# Encapsulation



Luckily you can configure it globally when bootstrapping your app:

```typescript
platformBrowserDynamic().bootstrapModule(AppModule, [
  {
    // NOTE: Use ViewEncapsulation.None only if you know what you're doing.
    defaultEncapsulation: ViewEncapsulation.None
  }
]);
```

- The default is ViewEncapsulation.Emulated
- Encapsulation: ViewEncapsulation.None
  - Overrides parent style
  - Style become global styles affect other components
   <img   src="https://github.com/ghoul007/snippets-Angular/blob/master/img/None.png">
- Encapsulation: ViewEncapsulation.Emulated
  - Overrides parent style
  - Style Does not become global style at this time
  <img   src="https://github.com/ghoul007/snippets-Angular/blob/master/img/emulated.png">
- Encapsulation: ViewEncapsulation.ShadowDom (Native deprecated after version 6)
  -  Parent style does not work
