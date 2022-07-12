# Render-Props

Imagine Your building and App which people see dogs and voting them. you're going to get the dogs pics from an `API`. So, I'm going to create a Puppy feed component.

So, what I'm going to do.

1. GET/api/puppies
2. Surface 'loading' spinner
3. Render adorable puppies
4. If error, render error

So we have a component and we pass `dogs`, `cats` as prop and we get those pictures

```js
<Puppies pet="kittens" />
<Puppies pet="puppies" />
```

Now they come to you and say they want a UserProfile

1. GET/api/profile
2. Surface 'loading' spinner
3. Render adorable puppies
4. If error, render error

So as you can see this pattern is very similar to the previous one.

it's actually the same thing as pets, except it's renders Priles instead of dogs.

maybe the presentation of this component going to be different, maybe it's going to have input's and some other things. or maybe you manager comes to you and says, ohh I have this awesome idea, we wanna have a different loading spinner here, And so you think like, ohh, well actually they're like the same component, and I don't know maybe I need to add a conditional statement in the component, if it pet is equal to puppy, then show that or kitten, and you notice that your component is bloating.

A design pattern is a general repeatable solution to a commonly occuring problem in software design.

In React it is mostly to solve an issue regarding rendering and passing props with ease.

`tight coupling of logic + presentation made our component less reusable and flexible`

and because we connected our logic and presentation to each other we kind og backed into a corner,

**So the solution to this is a pattern called render props**

`Render Props`:
is a simple technique for sharing code between React components.

```js
<MyComponent render={(data)=> 
  <div>{data}</div>
}/>
```

`render could be in any name`

As we see in these components:

*What they have in common:

1. Request Data from API
2. Need Loading States
3. Have error states

*How they differ?

1. Render different things
2. Render different spinners

common logic different presentation


*How it works

For components that needs to share state with other encapsulated components without creating a different component.

### Example without render prop

