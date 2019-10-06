# Hostlistener

 global event listeners in your Components/Directives with HostListener

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

you can have a mutiple listeners

```typescript

@HostListener('window:keydown.ArrowRight')
@HostListener('window:keydown.PageDown')
next() {
  console.log('Next')
}
```

and we can pass a params
```typescript
@HostListener('window:keydown.ArrowRight', '$event.target')
next(target) {
  console.log('Pressed right on this element: ' + target)
}
```