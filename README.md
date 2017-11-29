# ionic-test-case
Test case for ionic team

To recreate the project:


1) ionic start myApp tabs
2) ionic g page testpage


### Contents of home.ts

```
import { Component } from '@angular/core';
import { NavController, App } from 'ionic-angular';

@Component({
  selector: 'page-home',
  templateUrl: 'home.html'
})
export class HomePage {

  constructor(
    public navCtrl: NavController,
    public app: App
  ) {

  }

  clickA() {
    this.app.getRootNavs()[0].push('TestpagePage');
  }

  clickB() {
    this.navCtrl.push('TestpagePage');
  }

}


```

### Contents of home.html

```
<ion-header>
  <ion-navbar>
    <ion-title>Home</ion-title>
  </ion-navbar>
</ion-header>

<ion-content padding>
  <h2>Welcome to Ionic!</h2>
  <p>
    This starter project comes with simple tabs-based layout for apps
    that are going to primarily use a Tabbed UI.
  </p>
  <p>
    Take a look at the <code>src/pages/</code> directory to add or change tabs,
    update any existing page or create new pages.
  </p>

  <button ion-button (click)="clickA()">Push to Root nav (Can't swipe back)</button>
  <button ion-button (click)="clickB()">Push to Nav (can swipe back)</button>
</ion-content>


```