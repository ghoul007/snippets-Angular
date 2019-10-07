# Global Event
add global event listeners in your Components/Directives with HostListener

```typescript
@Directive({
  selector: '[rightClicker]'
})
export class ShortcutsDirective {
  @HostListener('window:keydown.ArrowRight')
  doImportantThings() {
    console.log('You pressed right');
  }
}
```

You can have multiple bindings:

```typescript
@HostListener('window:keydown.ArrowRight')
@HostListener('window:keydown.PageDown')
next() {
  console.log('Next')
}
```

You can also pass params:

```typescript
@HostListener('window:keydown.ArrowRight', '$event.target')
next(target) {
  console.log('Pressed right on this element: ' + target)
}
```