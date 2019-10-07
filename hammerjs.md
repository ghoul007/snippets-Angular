#Gesture with hammer js

some examples with hammerjs

```typescript

  <!-- pan events -->
  <div (pan)="logEvent($event)"></div>
  <div (panstart)="logEvent($event)"></div>
  <div (panmove)="logEvent($event)"></div>
  <div (panend)="logEvent($event)"></div>
  <div (pancancel)="logEvent($event)"></div>
  <div (panleft)="logEvent($event)"></div>
  <div (panright)="logEvent($event)"></div>
  <div (panup)="logEvent($event)"></div>
  <div (pandown)="logEvent($event)"></div>

  <!-- pinch events -->
  <div (pinch)="logEvent($event)"></div>
  <div (pinchstart)="logEvent($event)"></div>
  <div (pinchmove)="logEvent($event)"></div>
  <div (pinchend)="logEvent($event)"></div>
  <div (pinchcancel)="logEvent($event)"></div>
  <div (pinchin)="logEvent($event)"></div>
  <div (pinchout)="logEvent($event)"></div>

  <!-- press events -->
  <div (press)="logEvent($event)"></div>
  <div (pressup)="logEvent($event)"></div>

  <!-- rotate events -->
  <div (rotate)="logEvent($event)"></div>
  <div (rotatestart)="logEvent($event)"></div>
  <div (rotatemove)="logEvent($event)"></div>
  <div (rotateend)="logEvent($event)"></div>
  <div (rotatecancel)="logEvent($event)"></div>

  <!-- swipe events -->
  <div (swipe)="logEvent($event)"></div>
  <div (swipeleft)="logEvent($event)"></div>
  <div (swiperight)="logEvent($event)"></div>
  <div (swipeup)="logEvent($event)"></div>
  <div (swipedown)="logEvent($event)"></div>

  <!-- tap event -->
  <div (tap)="logEvent($event)"></div>

  ```