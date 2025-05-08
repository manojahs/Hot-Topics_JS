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


