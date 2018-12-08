# Ngx Hotjar

An easy implementation to track hotjar on angular6+ apps.

**@TODO:** 
* Create an Ng Router Helper;
* Create unit tests;

## Install

```
npm install ngx-hotjar
```

## Feedbacks

https://github.com/maxandriani/ngx-hotjar

## Simple Configuration

```ts
import { NgxHotjarModule } from 'ngx-hotjar';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    NgxHotjarModule.forRoot('traking-code')
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## Virtual Page Views

```ts
class Component implements OnInit {
  constructor(
    protected $hotjar: NgxHotjarService
  ) {}

  ngOnInit() {
    this.$hotjar.virtualPageView('/virtual/component/started');
  }
}
```

## Trigger events

```ts
class component implements OnInit {
  constructor(
    protected $hotjar: NgxHotjarService
  ) {}

  ngOnInit() {
    this.$hotjar.trigger('my-event');
  }
}
```

## Trigger Page Navigation

```ts
class component implements OnInit {
  constructor(
    protected $hotjar: NgxHotjarService
  ) {}

  ngOnInit() {
    this.$hotjar.stateChange(`${$router.urlAlterRedirects}`);
  }
}
```