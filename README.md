# angular-notes
It covers some imp revision notes required for angular.
1. Till nov22 latest version is 15.0.0. i have worked on angular 6.<br>
2. Angular is typescript based binding framework which binds html view with javascript object. hence it also called MVVM design pattern, where M is model and v is view and angular work as view-model binder. It also helps to build single page app by using routing. and it uses type-script language.<br>
3. Angular js vs angular -> 1.x is angular js and post version 2 it is called angular.angularjs is based on javascript language, Angular is based on typescript language. Angularjs is based on controller based architecture, angular is build on component based architecture.angular also has cli by which we can create angular modules easily.<br>
4. Component are basic building block of angular. each component has ui and ts class. component decorator contains selector,templateUrl,styleUrls. and class can contain data-fields which can be used inside template html. CLI command to create component -> ng generate component <component-name> <br>
It will create -> <br>
4.1 A directory named after the component <br>
4.2 A component file, <component-name>.component.ts <br>
4.3 A template file, <component-name>.component.html <br>
4.4 A CSS file, <component-name>.component.css <br>
4.5 A testing specification file, <component-name>.component.spec.ts<br>
5. Directives are angular syntax which we write inside html tags. by it the behavior of HTML DOM can be changed dynamically. <input [(ngmodel)]="value" type="text" value=""> <div>{{value}}</div> . Here if someone type somthing in input text. it will be displayed directly below that.<br>
6. three types of directives in angular. SAC - structural, attribute and component. <br>
6.1 structural ->
*ngFor and *ngIf are structural. by it dom structure gets decided.<br>
6.2 attribute -> in it element will remain in DOM structure just it decide appearance or behavior (styling) of that element. like enable/disable attribute will hide button but will remain part of dom.<br>
6.3 Angular components are actually just directives under the hood. it is different from other 2 in a way that it also has template.@Component meta-data annotation is used to create it.<br>
We can also create custom directive (here ui is optional) by using @Directive meta-data annotation.<br> 
7. npm is a node package manager by which we can install any java script framework like jquery,typescript. node_modules is folder inside which npm will install packages. npm install jquery<br>
8. package.json file is a file where we have all the javascript references(like jquery 3.4.1 version, tslib 1.10.0 version) is mentioned. by it all the required dependency with desired version will be downloaded together in one go.<br> 
9. typescript extends javascript and provides more types and scrict checks.it also make it easier to implement oops concepts, like creating class inheritance etc.<br> 
10. Angular provide CLI by which we can easily generate required components, services via single command. ng new my-app. it will create project with ready-made structure and template.<br> 
11. Module groups multiple components together. and by it we can also implement lazy loading. By using @NgModule we can create module. ng generate module moduleName<br> 
12. decarator provide info to angular that what type of class it is. @Component is used to create ts class with info like selector, css, template.<br> 
13. Template is a HTML view of angular component. inside @Component we can either create in-line template or can pass template file using templateUrl.<br>
14. Data binding describe how view and component communicate with each other. 4 Types of data binding -><br>
one way data binding-> here changes of model is reflected to the view. data flows only in one direction i.e from the models to the views<br>
14.1 Expression/interpolation binding: < img src="{{image}}"> . here we can pass model inside {{}} in html.<br>
14.2 Property Binding -> <img [src] ="image" > here the src property of the img element is bound to a component’s image property. as we can see both can be used interchangeably. but when non-string value is needed to be set you must use Property binding and not Interpolation<br>
14.3 event binding -> <button (click)="goBack()">Go back</button> . by it we can listen to certain events such as mouse movements<br>
14.4 two way binding -> <input [(ngModel)]="course.name" placeholder="name"/> . here it is combo of property and event binding and hence changes from ui is reflected to model and vice versa.<br>
14.5 Angular architecture -> 1 template - html view of angular, 2 component - bind view with model, 3 modules - group component together, 4 binding - defined how view and component communicate, 5 directives - changes the html dom behaviour, 6 service - helps to share common logic accross modules (it does not has template), 7. dependency injection - injects component via constructor. <br>

15. SPA is single page application. here ui loaded once and then some part is refreshed acc to angular routing.<br>
16. Routing define navigation. ng new customer-app --routing. it will create application and also  app-routing.module.ts
implentation -> <br>
16.1 step 1-> create ts class which has list of json objects , where each obj has 2 things, path(defines url) and component to load when url is clicked. <br>
export const HomeRoutes = [{path: 'home',component: HomeComponent}]<br>
16.2 step 2-> in html suppose on click of anchor tag we want to open html page refer by HomeComponent. <a [routerLink]="['home']">Home</a> <br>
We can also perform routing from component class by using this.route.navigate(['/home']);<br>
16.3 step 3-> in html define <router-outlet></router-outlet>. this is the place where HomeComponent view is rendered when anchor tag is clicked. <br>
17. angular can follows lazy loading. i.e. only necessary html, css and js files are loaded initially and on click of some event next view is loaded. To do that divide your project into different modules. if there is only 1 module lazy loading is not possible. after diviidng project into modules, then in routing ts class define loadChildren alogn with route path<br>
export const HomeRoutes = [{path: 'home',loadChildren: '../CustApp/CustApp.Module#CustomerModule'}]<br>
18. dependency injection can be implemented by adding entry inside providers property of @NgModule metadata. here we specify  name to be used as 'provide' attribute and component name under 'useClass'. then in class where we want to inject. provide entry in constructor with name as specified in 'provide'.<br>
19. ng serve vs ng build -> ng serve builds in memory and does not generate build in dist folder. it is used in dev stage where we want to fast deploy changes. ng build create build and save it into dist folder.so that your app can be deployed to remote server.<br>
ng build --prod. is used in production. it will create compress js files and remove un-necessary comments before generating artifact.and make it prod ready.<br>
20. How angular app starts-> https://www.javatpoint.com/how-an-angular-app-get-loaded-and-started <br>
Angular process angular.json. Here inside build step main.ts is mentioned. hence main.ts is the entry point. inside it AppModule loading call is mentioned. inside app.module.ts file, it get AppComponent, so it runs app.component.ts file where html file app.component.html is mentioned and also selector as app-root mentioned. now when request comes first index.html is loaded and inside it <app-root></app-root> tag is there, it replaces it with content of app.component.html<br>
main.ts  >>   app.Module.ts  >>  app.component.ts  >>  index.html  >>  app.component.html <br>