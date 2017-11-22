## Directives

>Angular templates are dynamic. When Angular renders them, it transforms the DOM according to the instructions given by directives.
A directive is a class with a @Directive decorator. A component is a directive-with-a-template; a @Component decorator is actually a @Directive decorator extended with template-oriented features.
> - [Angular Guide](https://angular.io/guide/architecture#directives)

So, there are three kinds of **directives**: 
- component
- structural
- attribute

### Component Directives

As we've seen before, the **component directives** are **directives** with templates. This is the most common to use.

### Structural and Attribute Directives

According to the [Angular Guide](https://angular.io/guide/architecture#directives), **structural** and **attribute** directives tend to appear within an element tag as attributes do, sometimes by name but more often as the target of an assignment or a binding.

#### Structural

The **structural** directives can transform/alter layout by adding, removing and replacing the template and the DOM structure.

##### ngIf

The Angular **ngIf** directive is used to display a view or portion of a view. It inserts or removes an element based on a *trythy/falsy* condition.

###### Example

```typescript
<input type="text" [value]="user.name">
<div *ngIf="user.isPremium">
	Welcome to the premium access!
</div>
```

##### ngFor

The Angular **ngFor** is the *Angular repeater* directive.

###### Example

In the example bellow, the **ngFor** will repeat the *<li>* element for each user in the *users* group of our class.

```typescript
export class AppUsers {
  title = 'My App Users';
  userse = ['tommy', 'dave', 'bob', 'john'];
}
```

```angular
<ul>
	<li *ngFor="let user of users">{{user.name}}</li>
</ul>
```


#### Attribute

The **attribute** directives can transform the appearance or behavior of an existing element. In templates they look like regular HTML attributes.
