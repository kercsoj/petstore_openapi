# Page 2

```runkit nodeVersion="18.x.x"
// Let's show where the Internation Space Station currently is.
console.log("Let's see where the ISS is with Node " + process.version);

// We can use any package from NPM since they are all built in.
var getJSON = require("async-get-json"); 

// And we can use ES7 async/await to pull the ISS's position from the open API.
var result = await getJSON("http://api.open-notify.org/iss-now.json");

// RunKit will automatically display the last statement and try to find its best representation:
result.iss_position;

```
