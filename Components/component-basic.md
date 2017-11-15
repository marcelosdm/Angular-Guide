# Component (a basic introduction)

To be simple, we can say that **Components** are custom elements. That is, **components** are small independent and reusable parts.
Usually, it contains a *selector* and a *template*:

+ **selector** - this is the *name* we give for the application to use as a *tag*
+ **template** - this is where we define the appearance of the component

To better understand the use of a component, imagine that a page in an application can be composed of several components. For example: 

+ the app component
++ header (inside the app)
  + content (inside the app)
  + shopping (inside the app)
    + item (inside the shopping)

So, we can see that a page is made up by small parts (components), that can operate independently or communicate with each other and are distrubuted in tree structure, where at the root there's always a parent component, followed by its children.

## Defining a component

To define a component, it is used the **ES 2015** syntax with the **TypeScript** sintax. See the example:

```javascript
export class MyComponent {
	constructor() {}
}
```
Note that the sample component above uses the *export* keyword, so that it can be used by other application configuration files, that is, it becomes an **ES 2015** module.

There are other things to report to Angular. For example: *what is the name of the tag we want to use for this component?*

For this, we must first use the *decorator* **@Component**. In it, some *[metadata properties](https://angular.io/api/core/Component)* can be informed:

+ **selector** - is the *tag* or the css selector that identifies this component in a template
+ **template** - inline-defined template for the view
+ **templateUrl** - url to an external file containing a template for the view

See more on the [Angular Documentation](https://angular.io/api/core/Component)

Let's take a look in an example of a basic statement of a component:

```javascript
@Component({
	selector: 'app-first',
	templateUrl: './myfirst.component.html'
})

export class MyComponent {
	constructor() {}
}
```

When we use the *template*, the HTML code is typed into the metadata itself. However, its use is recommended only if the template is small and simple. It also can be declared in multiple lines, using **template strings**, using *backtick* **`**.

```javascript
@Component({
	selector: 'app-first',
	template: `<h1>
                    My Component
                </h1>`
})

export class MyComponent {
	constructor() {}
}
```

Templates may also contain expressions that resolve the properties of the component itself. That is called **template interpolation**. Note that in the example bellow, we've got two different properties. The `title`, which is a property itself, and the `user.name`, which is the property *name* of the *user* object.
 
```javascript
@Component({
	selector: 'app-first',
	template: `<h1>{{title}}</h1>
		  <p>Welcome, {{user.name}}!</p>`
})

export class MyComponent {
	
	title: string = 'My Component Title'

	user = {name: 'Marcelo'}
}
```

## Creating a Component using Angular-CLI

Sometimes, the quickiest and easiest way to develop something in **Angular** is by using its **CLI** (*Command Line Interface*).

Here is a simple step to create a **component**, using the **Angular-CLI**:

+ On the *terminal*, type `ng generate component component_name`. Or to simplify the command can be shortened to `ng g c component_name`

Once done, four files will be generated in the application:

1. a **HTML** file (the component's **template**);
2. a **CSS** file;
3. a **TS** file (the component itself).
4. another **TS** file, but this one is a *spec* file, that is, for testing.

If the developer doesn't want to create a *spec* file, it's possible to generate the component without it, by typing `--spec=false` in the end of the commmand. Then it would look like this:

```
ng g c component_name --spec=false
```

All of them are created inside a folder, which by default has the name of the component.

Another thing that is important to know, is that in the **app.module.ts** file, the new component is automatically listed on the *declarations*. This saves the developer from having to remember to inform this parameter.

### Using the generated Component

Now, we can use the **component's selector**, or its *tag* as many say. In any template file, the developer just need to declare this selector as an HTML tag. Remember: this selector is defined in the component's **TS** file, in the *metadata* **selector**, inside the *decorator* **@Component**.

For example, let's see how the *app-first* selector of the component we saw earlier would be used by another template:

```html
<app-first></app-first>

```
Really simple, isn't it? :alien:

### Styling the Component

Everything that's made in the component's CSS file, will be automatically updated to the templates where the selector is. But attention: to create the styles, you must use the CSS selectors based on the component's HTML template.
