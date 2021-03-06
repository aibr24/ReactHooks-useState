# Hooks - useState()

## Discussion

**Topics to discuss**:
* State
* Using useState()
* Naming Convention



# State

**What is a State?**:
* A state contains observable data that may change over time. So this is perfect for variables that might be updated frequently and are rendered to the user.

**What is so special about State?**:
- Changes in state trigger a re-render in react, so if we are rendering data to the user that might be subject to change,
state would be the man for the job. Instead of having to reload the webpage and send a new request, we can harness the power
of react and re-render the page applying the changes.



# Using useState( )

The first step is to import the hook from our library:

```javascript
// Don't forget the curly brackets
import React, { useState } from "react";


```

Then we define the state inside our function, otherwise we would encounter an error: 
```javascript
//Our import
import React, { useState } from "react";


// The function
function App(){

// Defining our state
const [state, setState] = useState("initial value")

return;
}


export default App;
```

# Naming Convention
The correct naming convetion is to use camelCase when naming your variable("current state") and function, and in the case of the hook itself its a reserved name
so it must be written in that same way.

**A couple of examples**

 	
  &#10060;
```javascript
// PascalCase
const [Variable, SetVariable] = UseState(0);

```
 
 &#10004;
```javascript
//camelCase is the correct naming convention
const [variableOne, setVariable] = useState(0);

```


## Creating a simple counter
Now let's try writing a simple counter to see how all this works.

**Lets start by attempting to write it wihtout using states to truly understand what the state helps us acheive :**
```javascript
import React from "react";


function App(){
// defining a variable for our counter's initial value.
let counter = 0;

//creating a function that incriments our counter and logs it.
const handleIncrement = () => {
    console.log(counter)
    return counter++;
  };

return return (
    <div>
      <header>{counter}</header>
      <button onClick={() => handleIncrement()}>+</button>
    </div>
  );
}


export default App;
```
*as you can see it shows on the console but the data is not changing on screen for the user*

**Now let's make one using the useState hook :**

```javascript
// Imports
import React, { useState } from "react";


function App() {
  // The state
  const [count, setCount] = useState(0);

  // The functions
  const handleIncrement = () => {
    setCount(count + 1);
  };

  const handleDecrement = () => {
    setCount(count - 1);
  };

  return (
    <div>
      <header>{count}</header>
      <hr />
      <button onClick={() => handleIncrement()}>INCREMENT</button>
      <button onClick={() => handleDecrement()}>Decrement</button>
    </div>
  );
}

export default App;
```
*Voilà*



# Task :

Define a useState with an initial value of false, 
and create an element that would be rendered only if the state is true.
The element can be anything of your choice.

**Steps**

1. Impport the useState hook
<details>
  <summary>Example</summary>

  ```javascript
  import react, {useState} from "react"
  ```
</details>

2. Define the state inside your component

<details>
  <summary>Example</summary>

  ```javascript
  import react, {useState} from "react"
  
  
  const Component = () => {
  const [state, setState] = useState("initial state")
  
  }
  ```
</details>

3. Create a button that changes the states value

<details>
 <summary>Spoiler</summary>
 
 ```javascript
 <div>
     <button onClick={() => setState(!state)}>!</button>
 </div>
```

</details>

4. Create a conditionaly rendered element that relies on the states value

<details>
  <summary>Spoiler</summary>

  ```javascript
  import React, { useState } from "react";
  
  
  function App() {
  const [state, setState] = useState(false)
  
  return(
   <div>
      <button onClick={() => setState(!state)}>!</button>
      <div>{state ? ("hello") : null}</div>
      <hr/>
   </div>
  )
  
  }

export default App;
  ```
</details>



