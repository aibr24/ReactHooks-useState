# Hooks - useState()

## Discussion

**Topics to discuss**:
* State
* Using useState()
* Naming Convention



# State

**What is a State?**:
* The state contains data that may change over time. So this is perfect for variables that might be changed frequently.

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

**a couple of examples**

 	
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
      <button onClick={() => handleIncrement()}>REGINCREMENT</button>
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
    setCount((prevCount) => prevCount + 1);
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


