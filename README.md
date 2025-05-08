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
