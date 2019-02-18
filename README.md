# demo-ng-modules
demo of using angular modules

# install package
npm install bootstrap --save

# create student module
ng g module student

# create components under student module
ng g c student/student --spec=false
ng g c student/student-list --spec=false
ng g c student/student-list-item --spec=false

# declartion in studen module

declarations should be used to declare what components in the module

```
@NgModule({
  declarations: [StudentComponent, StudentListComponent, StudentListItemComponent],
  imports: [
    CommonModule
  ]
})
```

import the student module to the app module
```
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    StudentModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

# create service and model

ng g s student/student --spec=false

create student.model.ts

```
export class Student {
  id: Number;
  name: String;
  enrollno: Number;
  college: String;
  university: String;
}

```

modify the student service which will be used to provide some students data in observable format

observable tutorial: 
- https://appdividend.com/2018/12/08/angular-7-observables-tutorial-with-example/
- https://gist.github.com/staltz/868e7e9bc2a7b8c1f754



