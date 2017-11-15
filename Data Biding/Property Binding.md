## Property Binding

>Write a template property binding to set a property of a view element. The binding sets the property to the value of a template expression.

[Angular Documentation](https://angular.io/guide/template-syntax#property-binding--property-)

The sintax is used with brackets **[]** around the property that will have the assigned value and can be applied to any element of the *DOM*.

Let's see the example, to better understand:

1. See the property **name** of the **player** object, in the component:

```typescript
player = {name: 'Kobe Bryant'}
```

2. Now, take a look in the componet's template, where we're using the **property binding** in an *input* element:

```html
<input type="text" [value]="user.name">
```

Ok good, but there's one more thing to consider! Everytime that the player name is changed in the component, it will be updated in the template too, because they are *binded*(connected)! That's magic! :tophat:

This is what we call **one-way databinding**. 

>People often describe property binding as one-way data binding because it flows a value in one direction, from a component's data property into a target element property.

That's the [One-way in](https://angular.io/guide/template-syntax#one-way-in) definition, in the **Angular Documentation**.

So, to resume we can say that the binding is always made from the component to the template.

### Examples

Let's see another example. 

In this one, the *div* in the template is hidden, and only will be shown for the users that has the *isPremium* property set to *true*.

```typescript
//in component

user = {name: 'Harry',
	isPremium: true}
```

```typescript
<!-- in template -->

<input type="text" [value]="user.name">

<div [hidden]="!user.isPremium">
	Premium Stuff
</div>
```
