
# Get diffrent type with ViewChild

It's possible to use @ViewChild (also @ViewChildren and @ContentChild/Children) to query for components of different types using dependency injection.


```typescript

abstract class Base {}

@Component({
  selector: 'foo',
  providers: [{ provide: Base, useExisting: Foo }]
})
class Foo extends Base {}

@Component({
  selector: 'bar',
  providers: [{ provide: Base, useExisting: Bar }]
})
class Bar extends Base {}

// Now we can require both types of components using Base.
@Component({ template: `<foo></foo><bar></bar>` })
class AppComponent {
  @ViewChildren(Base) components: QueryList<Base>;
}
```

[Working Demo](https://stackblitz.com/edit/angular-stthrl)