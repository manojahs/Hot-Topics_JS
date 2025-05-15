# Hot-Topics_JS
----------------------
Serialization and deserialization in js
------------------------------
Serialization is converting object to json,xml format

const user = {
  name: "Alice",
  age: 30
};

const jsonString = JSON.stringify(user); 

-----------------------------------------------
deserialization is converting the converted json to object format

const jsonString = '{"name":"Alice","age":30}';
const user = JSON.parse(jsonString); 


Shallow Copy and Deep Copy
---------------------------
A shallow copy copies only the top-level properties. If the original object contains nested objects, they are not copied, just referenced.


const original = {
  name: "Alice",
  address: {
    city: "Paris"
  }
};

const shallowCopy = { ...original };

shallowCopy.name = "Bob";
shallowCopy.address.city = "London";

console.log(original.name);           // "Alice" → unchanged
console.log(original.address.city);   // "London" → changed!

------------

A deep copy creates a new object recursively, duplicating all nested objects and arrays.

const original = {
  name: "Alice",
  address: {
    city: "Paris"
  }
};

const deepCopy = JSON.parse(JSON.stringify(original));   or const deepCopy = structuredClone(original);  // ✅ Supported in modern browsers


deepCopy.name = "Bob";
deepCopy.address.city = "London";

console.log(original.name);           // "Alice" → unchanged
console.log(original.address.city);   // "Paris" → unchanged

Async and defer what are these?
---------------------------------

Async and defer are HTML attributes used with the <script> tag that control how JavaScript files are loaded and executed in relation to the rest of the webpage.

async attribute:
--------------
Downloads the script in parallel with HTML parsing
Executes the script as soon as it's downloaded, interrupting HTML parsing
Execution order is not guaranteed (whichever script finishes downloading first runs first)
Best for independent scripts that don't rely on DOM elements or other scripts

defer attribute:
------------------
Downloads the script in parallel with HTML parsing
Executes only after HTML parsing is complete, but before the DOMContentLoaded event
Maintains script execution order as they appear in the document
Best for scripts that need the DOM or depend on other scripts running in a specific order

Debounce vs throttling 
------------------------

Debouncing
-----------
ensures a function is called only after a specified delay since the last time it was invoked. It’s useful when you want to limit the number of times a function fires until a user stops performing an action.

 Use Case:
 ------------
Typing in a search box (triggering an API call only when user stops typing)

Throttling 
------------
ensures a function is called at most once in a specified time interval, no matter how many times the event occurs.

Use Case:
---------
Handling window resize or scroll events efficiently.

How do you prevent default behavior in an event?
Ans: event.preventDefault();

Session storage vs Localstorage vs cookies
-----------------------------------------------

localStorage
---------------------
Key Characteristics:

Persists indefinitely until explicitly cleared
Stores approximately 5-10MB of data (varies by browser)
Never sent to the server automatically
Same-origin policy (domain, protocol, port)
Synchronous API

Shared storage space:
---------------------
All tabs/windows from the same domain access the same localStorage repository

Real-time updates: Changes made in one tab can be detected in other open tabs/windows

Same-origin requirement:The sharing only works within the same domain, protocol (HTTP/HTTPS), and port

 sessionStorage:
-------------------------------------------

Tab-specific storage: Each tab or window has its own separate sessionStorage instance

No cross-tab sharing: Data stored in sessionStorage is strictly confined to the tab where it was created

New tab = empty sessionStorage: Opening a new tab creates a fresh, empty sessionStorage, even if navigating to the same site

Duplicating tabs: Even when duplicating a tab (e.g., right-click > "Duplicate"), the new tab gets a fresh sessionStorage

Cookies
----------------------
Key Characteristics:

Configurable expiration (session or specific date)
Small capacity (4KB total for all cookies per domain)
Automatically sent with every HTTP request to the domain
Can be restricted to specific paths
Can be marked as HTTP-only (inaccessible to JavaScript)
Can be marked as Secure (only sent over HTTPS)
Can be set with SameSite attribute (CSRF protection)

<img width="560" alt="image" src="https://github.com/user-attachments/assets/d3296b00-fa04-4cba-8e2e-6495732d02be" />


