# RouterLink params

the router will navigate to `/first/details`
```typescript
<a [routerLink]="['/', 'first','details']">
  link with params
</a>
```


the router will navigate to `/first;name=foo/details`
```typescript
<a [routerLink]="['/', 'first', {name: 'foo'}, 'details']">
  link with params
</a>
```



the router will navigate to `/first;name=foo/details?q=new`
```typescript
<a [routerLink]="['/', 'first', {name: 'foo'}, 'details']" [queryParams]=" { q: 'new'}">
  link with params
</a>
```