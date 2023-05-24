# House-Rent-Angular-Appllication
simple Angular app that lists houses for rent and show the details of individual houses : 

Step 1 - Identify the version of node.js that Angular requires : node --version
Step 2 - Install the correct version of node.js for Angular
Step 3 - Install the latest version of Angular : npm install -g @angular/cli
Step 4 - Install integrated development environment (IDE) : Visual Studio Code

# Step 1 - Test the default app :
1. In your project directory, navigate to the first-app directory.
2. Run this command to install the dependencies needed to run the app : npm install
3. Run this command to build and serve the default app : ng serve
4. In a web browser on your development computer, open http://localhost:4200.
5. Confirm that the default web site appears in the browser.
6. You can leave ng serve running for as you complete the next steps.

# Conceptual preview of Angular components : 
Angular apps are built around components, which are Angular's building blocks. Components contain the code, HTML layout, and CSS style information that provide the function and appearance of an element in the app. In Angular, components can contain other components. An app's functions and appearance can divided and partitioned into components.
In Lesson 1, you updated the AppComponent, whose function is to contain all the other components. In this lesson, you create a HomeComponent to display the home page of the app. In later lessons, you create more components to provide more features to the app.

In Angular, components have metadata that define its properties. When you create your HomeComponent, you use these properties:
1. selector: to describe how Angular refers to the component in templates.
2. standalone: to describe whether the component requires a ngModule.
3. imports: to describe the component's dependencies.
4. template: to describe the component's HTML markup and layout.
5. styleUrls: to list the URLs of the CSS files that the component users in an array.

# Step 2 - Create the HomeComponent : 
1. Run this command to create a new HomeComponent : ng generate component Home --standalone --inline-template --skip-tests
2. Run this command to build and serve your app : ng serve

Interfaces are custom data types for your app.
Angular uses TypeScript to take advantage of working in a strongly typed programming environment. Strong type checking reduces the likelihood of one element in your app sending incorrectly formatted data to another. Such type-mismatch errors are caught by the TypeScript compiler and many such errors can also be caught in your IDE.

# Step 3 - Create a new Angular interface :
1. In the first-app directory, run this command to create the new interface : ng generate interface housinglocation

# Conceptual preview of Inputs : 
Inputs allow components to share data. The direction of the data sharing is from parent component to child component.
To receive data from a parent component, a child component must mark a class property with the @Input() decorator. This decorator can be used in components and directives.
For a more in depth explanation, please refer to the Sharing data between child and parent directives and components guide.
In this lesson, you'll define @Input() properties in the HousingLocationComponent component which will enable you to customize the data displayed in the component.

You have to add the ! because the input is expecting the value to be passed. In this case, there is no default value. In our example application case we know that the value will be passed in - this is by design. The exclamation point is called the non-null assertion operator and it tells the TypeScript compiler that the value of this property won't be null or undefined.
 @Input decorators to properties in the HousingLocationComponent allow the component to receive data. In this lesson, you'll continue the process of sharing data from the parent component to the child component by binding data to those properties in the template.

When adding a property binding to a component tag, we use the [attribute] = "value" syntax to notify Angular that the assigned value should be treated as a property from the component class and not a string value.

# Conceptual preview of interpolation : 
you added data binding to the template to enable developers to pass data from the HomeComponent to the HousingLocationComponent. The next step is to display values (properties and Input values) in a template. In order to accomplish this task you have to use interpolation.
The Angular template syntax supports mixing static template content with dynamic values and expressions.
Using the {{ expression }} in Angular templates, you can render values from properties, Inputs and valid JavaScript expressions.

# Use *ngFor to list objects in component : 
In Angular, ngFor is a specific type of directive used to dynamically repeat data in a template. In plain JavaScript you would use a for loop - ngFor provides similar functionality for Angular templates. We use Angular template syntax to specify the details for the directive.
You can utilize ngFor to iterate over arrays and even asynchronous values. In this lesson, you'll add a new array of data to iterate over.

# Angular services :
Your app has a service to serve the data to your app. At the end of this lesson, the service reads data from local, static data. In a later lesson, you update the service to get data from a web service.
- Angular services 
Angular services provide a way for you to separate Angular app data and functions that can be used by multiple components in your app. To be used by multiple components, a service must be made injectable. Services that are injectable and used by a component become dependencies of that component. The component depends on those services and can't function without them.

- Dependency injection
Dependency injection is the mechanism that manages the dependencies of an app's components and the services that other components can use.
# Step - Create a new service for your app : 
1. Run this command to create the new service : ng generate service housing --skip-tests

# Add routes to the application :
Routing is the ability to navigate from one component in the application to another. In single page applications (SPA), only parts of the page is updated to represent the requested view for the user.
The Angular Router enables users to declare routes and specify which component should be displayed on the screen if that route is requested by the application.

# Conceptual preview of routing with route parameters : 
In the previous lesson, you added routing to your app and in this lesson you will expand the types of routing your app supports. Each housing location has specific details that should be displayed when a user navigates to the details page for that item. To accomplish this goal, you will need to use route parameters.
Route parameters enable you to include dynamic information as a part of your route URL. To identify which housing location a user has clicked on you will use the id property of the HousingLocation type.

# Add HTTP communication to your app
This tutorial demonstrates how to integrate HTTP and an API into your app.
Up until this point your app has read data from a static array in an Angular service. The next step is to use a JSON server that your app will communicate with over HTTP. The HTTP request will simulate the experience of working with data from a server.
