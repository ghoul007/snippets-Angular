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

## Others

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

## Example debug panel component
TS File
  ```typescript
  @Component({
    // tslint:disable-next-line:component-selector
    selector: "debug-panel",
    templateUrl: "./debug-panel.component.html",
    styleUrls: ["./debug-panel.component.scss"]
})
export class DebugPanelComponent implements OnInit {
    @Input() data;
    @HostBinding("class.has-content")
    get content() {
        return this.hasContent;
    }
    hasContent = false;
    @HostBinding("class.is-visible")
    get visible() {
        return this.isVisible;
    }
    isVisible = false;

    ngOnInit() {
        this.hasContent = this.data;
    }
}
```
HTML file
```html
<input id="debugToggle" type="checkbox" (change)="isVisible = !isVisible;">
<label for="debugToggle"></label>
<div>
    <pre>{{ data | json }}</pre>
</div>
```


SCSS file
```scss
:host {
    display: none;
}

 :host.has-content {
    display: block;
    background-color: rgba(237, 119, 119, .9);
    position: fixed;
    top: 0;
    right: 50vw;
    z-index: 100000
}

 :host.is-visible {
    bottom: 0;
    min-width: 50%;
}

input[type=checkbox] {
    display: none;
}

label {
    display: block;
    text-align: center;
    height: 1.6em;
    padding: .4em;
    line-height: 1.3em;
}

label:before {
    content: "show debug";
    width: 100%;
    cursor: pointer;
}

input[type=checkbox]:checked+label:before {
    content: "hide debug";
}

 :host.is-visible div {
    display: block;
    height: calc(100% - 1.6em);
}

div {
    display: none;
    overflow: auto;
}

pre {
    font-size: 1em;
    padding: 20px;
    margin: 0;
}

```

[Working Demo](https://stackblitz.com/edit/angular-bg3xqs)