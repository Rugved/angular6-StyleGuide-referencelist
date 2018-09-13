# Coding and structure guideline for Angular 6

Please refer to official guide for full explanation [https://angular.io/guide/styleguide#style-guide](https://angular.io/guide/styleguide#style-guide) 

**General**
1.	All files service/components should have single responsibility principle (SRP)
2.	Limit 400 lines code per file 
3.	Define small function limit lines to 75

**Naming (Files & Symbol)**

4.	Name files based on “description”.”type”.”extension” i.e. sample.type.ts
5.	Use conventional types when creating files i.e. service.ts, component.ts
6.	Upper camel case for class name i.e. AppModule

`Export class AppModule { … }	App.component.ts`

7.	Put bootstrapping and platform logic in main.ts
8.	Put “–“ for component selector i.e. selector: ‘main-button’
9.	Use lower case and prefix component selector i.e. for button inside sample component  selector:sample-button
10.	Prefix and have camel case for directive name i.e. selector:[sampleValues]
11.	Provide lowercase names i.e. ‘sorting’
12.	Name the files with component.spec.ts i.e. sample.component.spec.ts
13.	Provide feature name.module.ts naming convention i.e. sample.module.ts
14.	Class name should be in upper camel case i.e. SampleModule {}
15.	Provide routing module with –routing name. i.e. sample-routing.module.ts

**Coding Convention**

16.	Use Upper camel case for class name i.e. SampleModule
17.	Use Lower camel case for const i.e. export const appUrl = “”
18.	Use Upper camel case for interface i.e. ISample
19.	Use Lower camel case for properties and method names i.e. message:string, btnclick()
20.	Leave one-line space between thirdparty and app imports

**App structure**

21.	Organize code in LIFT style = Locate, Identify, flat, tdry (try to be dry (don’t repeat yourself)
22.	Locating code should be simple & fast
23.	Identifying folder, files etc should be easy
24.	Keep folder structure as flat as possible. Consider sub older after 7 files (psychologist believe human mind start to struggle once number of adjacent interesting things exceed nine)
25.	T-dry is try to don’t repeat yourself. Avoid duplicate code
26.	Create folder as per feature area, this will cover LIFT methodology
27.	Create ngModule for each feature for lazy loading
28.	Keep app module as root app module

**-	Shared Module**

29.	Create sharedmodule in shared folder
30.	Keep pipe, declarative in shared module to reference in the app
31.	Consider not keeping services in shared module as they are singleton and should be in core
32.	Lazy loaded shared module will have its own copy of component, keeping service inside there will have undesired result

**-	Core Module**


33.	Keep single use classes and services inside core module
34.	Import coremodule only inside app module as application wide module.
35.	Put guard so that other modules can’t import core module
36.	Never import lazy loaded module directly in another module

**Component**

37.	Use @input @output as property decorates instead of input and output
38.	Give component selector name not attribute
39.	Move style and html into their own file when code exceed more than 3 lines
40.	Keep properties on top of the methods
41.	Keep complicated logic inside services not inside component
42.	Keep logic of presentation inside the component, not inside html i.e. avoid this <html> a * b </html>
43.	Use directive to enhance element logic

**Services**

44.	Use services as singleton within same injector. 
45.	Use them to share data and functionality
46.	Provide service with @Injectable attribute in app root.
47.	Always interact with server through service
48.	Use life cycle hooks and interface to tap into import events provided by angular

**Coding helper**

49.	Use codelyzer for guideline and quick code generation as per this style
50.	Use angular 6 code snippet in vscode


