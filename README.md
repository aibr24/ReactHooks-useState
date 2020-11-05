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
const [variableOne, setVariable] = usestate(0);

```
