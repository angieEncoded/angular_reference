# Angular Notes

## Setting up a new project
- Make sure that the LTS version of NodeJS is installed
- Install the angular CLI using NPM
```npm install -g @angular/cli```

- Create an app
```ng new app-name```

- Serve the app
```ng serve```

- Generate a component in the app using the CLI
```ng generate component component-name```
- Note that the generator will typically prepend "app" to the component name
- So when you use the component after running, say, ```ng generate component primary-button``` the generator will have called the selector ```app-primary-button```

- Databinding in angular
  - Outputting data
    - String interpolation    ```{{data}}```
    - Property Binding    ```[Property]="data"```
  - Inputting data - reacting to user events with event binging
    - ```(event)="expression"```
  - Two way data binding
    - ```[(ngModel)]="data"```


# Angular notes

- Install the CLI
	- angular uses NodeJS to bundle (same as React)
	- ```npm install -g @angular/cli@latest```
	- This will install the latest version
- Create an angular project
	- Navigate to the target folder
	- ```ng new projectname --no-strict```
		- Start out in non-strict mode to make it easier to learn
- Serve up an angular project
	- ```ng serve```
- Get data from an input
	- ```ts
  		<input type="text" [(ngModel)]="name">
		<p>{{ name }}</p>
		```
- Install typescript
	- ```npm install typescript```
	- Install it into a project instead of globally
- run the typescript compiler
	- ```npx tsc filename.ts```
	- This will compile the target typrscript file into javacsript
- Listening for data on an input
    - Add the ngModel into app.module.ts
      	```ts
		import { AppComponent } from './app.component';
		import { BrowserModule } from '@angular/platform-browser';
		import {FormsModule} from '@angular/forms'
		import { NgModule } from '@angular/core';

		@NgModule({
		declarations: [
			AppComponent
		],
		imports: [
			BrowserModule,
			FormsModule
		],
		providers: [],
		bootstrap: [AppComponent]
		})
		export class AppModule { }```
	- Now we can use it in inputs
  	```ts
  		<!-- Tells angular to listen to anyting you input and store it in ngModel -->
		<input type="text" [(ngModel)]="name"> 
		<p>{{ name }}</p>```
- Installing things like bootstrap
  - It's just the same as with an express app 
  - ```npm install bootstrap@3```
  - This course is using a REALLY old version of bootstrap for some reason
  - Also try using ```npm install --legacy-peer-deps``` instead of npm install to correct some errors
  - 






- Basics
	```ts
		let age: number;
		let username: string 
		let isInstructor: boolean
		let hobbies: string[] // array 
		let person; // by default we can store 'any' value in a variable
		// defeats the purpose of even using typescript

		// Set up an object type - we can then only store an object that looks
		// like exactly that.
		let person: {
			name: string;
			age:number;
		};

		// create an array of objects
		let people: {
			name: string;
			age:number;
		}[];

		// type inference  -typescript will infer that we are using string
		// embrace the type inference feature
		let course = 'React - The Complete Guide';
		let course2: string = 'React - The Complete Guide'; // we can also specify

		// Union types - allows an arbitrary amount of types
		let unionType: string  | number;


		// Type aliases
		type PersonType = {
			name: string;
			age:number;
		};

		let myPerson: PersonType;
		let myPeople: PersonType[];


		// Function & types
		//  Types are inferred from return values but we can also manually set
		function add(a:number, b:number): number {
			return a + b;
		}

		// Special return type - when there is no return type it's void
		function printOutput(value: any){
			console.log(value)
		}

		// Generics
		function insertAtBeginning(array: any[], value:any ){
			const newArray = [value, ...array];
			return newArray;
		}

	```

	