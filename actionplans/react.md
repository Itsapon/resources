- install react app
- components and props
- state and useeffect
- routing

===SETUP===

---install react app---
  npx create-react-app nameOfApp
  cd into the newly created folder
  npm run start to start the server
You will already have a server built in, so you're good to go now. 
App.js => remove the fluff.
src/index.js => you find the app.js, with React wrapped around it. 


===COMPONENTS===
think about arcitecture. 
page: make page folder
component: make component folder. 
Everything you put in parent page/component will be visible in all the children. 
Syntax:
 //imports

 //function
export default function NameOfComponent(){
  everything it does needs to be above return.
  return (<div>
  If it just returns one line you don't need formatting. If it returns an object you need to use brackets first({}) so it knows it's an object and not a function</div>)
}
Add components to pages and components by: 
1. importing them 
import NameOfComponent from "./location/of/component"
2. plugging it
<NameOfComponent />

===PROPS===
1. in component: 
export default function Component(props) {
  return <div>{props.content}</div>
}
2. in parent: 
<div>
<Component content="some text here">
</div>

-- mapping with props: 
<ul>
{props.abilities.map((ability, index)=>{return <li key={index}>{ability}</li>})}
</ul>

===STATE USEEFFECT===
import { useState, useEffect } from "react";
- useState
- useEffect
useEffect(() => {
  console.log("The useEffect action!");
}, [numLikes]);
