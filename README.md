# angular-interview-help
It covers some imp revision notes required for angular.
1. Till nov22 latest version is 15.0.0. i have worked on angular 6.<br>
2. Angular is typescript based binding framework which binds html view with javascript object. hence it also called MVVM design pattern, where M is model and v is view and angular work as view-model binder. It also helps to build single page app by using routing. and it uses  language.<br>
3. Angular js vs angular -> 1.x is angular js and post version 2 it is called angular.angularjs is based on javascript language, Angular is based on typescript language. Angularjs is based on controller based architecture, angular is build on component based architecture.angular also has cli by which we can create component easily.<br>
4. Component are basic building block of angular. each component has ui and ts class. every component decorator contains selector,templateUrl,styleUrls. and class can contain fields which can be used inside template html. CLI command to create component -> ng generate component <component-name> <br>
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
We can also create custom directive (without ui) by using @Directive meta-data annotation.<br> 
7. npm is a package manager by which we can install any java script framework like jquery,typescript. node_modules is folder inside which npm will install packages. npm install jquery<br>
8. package.json file is a file where we have all the javascript references(like jquery 3.4.1 version, tslib 1.10.0 version) is mentioned. by it all the required dependency with desired version will be downloaded together in one go.<br> 
9. typescript extends javascript and provides more type and scrict checks.<br> 
10. 