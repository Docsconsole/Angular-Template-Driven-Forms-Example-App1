# Angular-Template-Driven-Forms-Example-App1
Angular-Template-Driven-Forms-Example-App1



app.component.html


<div class="container">
  <div class="row">
    <div class="col-md-8 offset-md-2">
      <form (ngSubmit)="onSubmit()" name="form" novalidate>
        <div class="form-group">
          <label for="firstName">First Name</label>
          <input #firstName="ngModel" [(ngModel)]="model.firstName" class="form-control" name="firstName" required
                 type="text"/>

        </div>
        <div class="form-group">
          <label for="lastName">Last Name</label>
          <input #lastName="ngModel" [(ngModel)]="model.lastName" class="form-control" name="lastName" required
                 type="text"/>

        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input #email="ngModel" [(ngModel)]="model.email" class="form-control" email name="email" required
                 type="text"/>

        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <input #password="ngModel" [(ngModel)]="model.password" class="form-control" minlength="6" name="password"
                 required type="password"/>

        </div>
        <div class="form-group">
          <button class="btn btn-primary">Register</button>
        </div>
      </form>
    </div>
  </div>
</div>

app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Angular-Template-Driven-Forms-Example-App1';
  model: any = {};

  onSubmit() {
    alert('SUCCESS!! :-)\n\n' + JSON.stringify(this.model))
  }

}

app.module.ts

import {BrowserModule} from '@angular/platform-browser';
import {NgModule} from '@angular/core';
import {FormsModule} from '@angular/forms';

import {AppComponent} from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule, FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {
}

