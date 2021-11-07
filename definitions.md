---State---
There are three different definitions of states:

1. application state: is a global state that is therefore accessible for all components/ trickles down thru props etc.
2. component state: a local state that is stored only in this component
3. redux state: a global state that is accessible thru redux store. All the initial states in a redux store together are called redux state.

---store---
A JavaScript Object that is different than a plain global object:

- you never modify directly or change a state inside the store
- you update state by creating an action object that says 'sth happened in application' and then dispatch this action to the store to tell what happened
- when an action is dispatched the store runs the root reducer function, which then lets it calculate the new state based on old state and action
- components in UI use selectors to extract data from store. These selectors are automatically kept up to date with data in store

---actions---
A regular JavaScript object that has two properties:

1. A type field. Aka an event that decsribes something that happened in the application.
   The type field should be a string that gives the action a descriptive name like "scoreboard/addPlayer". Convention of type field" "domain/eventName". First part is feature or category that the action belongs tom second part is what happened.
2. Payload. By convention put this info in a field called payload

---type field---
a string that gives an action a descriptive name. By convention, the first part should describe the redux slice that the action belongs to, the second part describes the action.
Example:
{type: "scoreboard/add"}

---payload---
additional field in an Action, where you put extra information about what happened.
Example:
{type: "scoreboard/add", payload: {name:"Robin",age:30}}

---dispatch---
In order to communicate with edux store you dispatch an action. This will make teh store update. You can think of it as 'triggering an event'.
Syntax:
const addPlayer ={
type: "scoreboard/newPlayer",
payload: {name:"Robin",age:30}
}
dispatch(addAction)

---reducer---
Basically an event listener
function that receives the current state and an action object, decides how to update state, returns new state.
(state, action) => newState
Reducers are pure functions.

---spread operator---
syntax: ...
Clones whatever you put after it:
const array2=[...array1]
array2 is now a copy of array1.
It also clones objects.

---refactoring---
the process of restructuring existing computer code, without changing its external behavior.

---boilerplate---
Set of tools that you add to your app to set it up
(react, axios, react-router etc)
"setting up the boilerplate"
Another word is skeleton.

---slices---
'categories' in your redux store. 5 is a lot. For instance, your products all together are 1 slice.
Often you have 2: users and products.

---switch function---
