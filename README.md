# 1.0 Release

### Setup Project
1. Create new project by Angular CLI
2. Integrate Bootstrap
3. Update main app template 
[[app.component.html]()]
4. Test: run project by CLI

### Main Process
1. Generate new Class by CLI 
[[common]()]
   - Declare attributes to match with JSON received from REST API 
2. Generate new Component by CLI (normally is a set of class entities) 
[[product-list]()]
3. Add new component selector to main template
4. Generate new Service by CLI: provide functions calling API then map data to the Component
[[services]()]
   - Inject HttpClient by constructor from ```@angular/common/http```: support HTTP methods
5. Import HttpClientModule from ```@angular/common/http``` and new Service (allow inject to other parts of the app) to main app module 
[[app.module.ts]()]
6. Update Component to subcribe data from the Service 
[[product-list.component.ts]()]
    - Inject the Service by constructor
7. Update Template to display data 
[[product-list-table.component.html]()]

# 2.0 Release
### Template Integration
1. Get sample templates including HTML and CSS files (work from front-end)
2. Install Bootstrap CSS style locally by CLI: ```npm install bootstrap```
3. Install Fontawesome for icons: ```npm install @fortawesome/fontawesome-free``` 
4. Verify installed entries in ```node_modules``` directory or ```package.json```
5. Inject CSS style entries globally by configurating ```styles``` in 
[angular.json]() 
6. Add CSS styles globally in 
[src/style.css]()
7. Restart app (if running) to make change with new configuration.
8. Integrate sample templates to the app templates 
[[app.component.html]()] [[product-list-grid.component.html]()]

### Routing
1. Define routes in the app module 
[[app.module.ts]()]
   - Use ** to for generic matching
   - First match wins: start from most specific to generic
   - Configure Route based on the defined routes in ```imports```: ```RouteModule.forRoot(<routes_name>)```
2. Define Router Outlet and setup Route Link in main template 
[[main.component.html]()]
3. Enhance Components in the routes to read param path (if there is) 
[[product-list.component.ts]()]
   - Add param as new property of the class
   - Inject ```ActivatedRoute``` (which loaded the Component) by the constructor for accessing route params
- Update Service method to get the params and call the appropriate API 
[[product.service.ts]()]

### Search Function
1. Create new component for search 
[[search]]
2. Add new route path for searching 
[[app.module.ts]()]
3. Update Search Component 
[[search.component.ts]()]
   - Inject the router (from ```@angular/router```)
   - Create a navigating method to navigate router to the search path
4. Update the Component and Service handling search method using API
[[list-product.component.ts]()] [[product.service.ts]()]
5. Update Search Template to call the navigating method of Search Component based on the events 
[[search.component.html]()]

# Notes
- @Injectable used for Service: allow the service to be injected into other classes/components.
- ```ngOnInit()``` of Class is similar to @PostConstruct.
- ```src/assets``` used to store resources: images, JS, CSS, etc.
- ```node_modules``` directory and ```package.json``` contain all the dependencies.
- ```angular.json``` is the main configuration file of the project.
- ```src/style.css``` is the global CSS style
- Use prefix ```+``` to convert string to number
- To view log, open Develop Tools/Inspect on the broswer (F12 for Chrome)







