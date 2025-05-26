<div>
<h1>Javascript</h1>

# Table of Contents

[Find a Value in an array of objects](#findinarrayobj)

[Javascript Switch](#javascriptswitch)

[Promise Chaining](#jsobjects)

[Promise](#promise)

[The JavaScript Switch Statement](#example2)

[upload file via upi](#fileuploadviaapi)

[JavaScript String charCodeAt()](#charcodeat)

[for Each](#foreach)

[node js with sqlite](#nodesqlite)

[Input In React](#inputinreact)

[use Context](#usecontext)

[setTimeout](#settimeout)

[Circular Loop Through Array](#circularloop)


# Find a value in an array of objects in Javascript <a name="findinarrayobj"></a>

```javascript
let arr = [
  { name: "string 1", value: "this", other: "that" },
  { name: "string 2", value: "this", other: "that" },
];

let obj = arr.find((o) => o.name === "string 1");

console.log(obj);
```

# The JavaScript Switch Statement <a name="javascriptswitch"></a>

```javascript
switch (expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
  // code block
}
```

# JavaScript String charCodeAt() <a name="charcodeat"></a>

```javascript
let text = "HELLO WORLD";
let char = text.charCodeAt(0);
```

# For Each Function <a name="foreach"></a>

```javascript
let num = [45, 454, 44, 4, 1, 4544, 44, 551, 1, 5];

num.forEach((v) => {
  console.log(v * v);
});
```

# setTimeout <a name="settimeout"></a>

```javascript
setTimeout(() => {
  console.log("2");
}, 5000);
```

# circular Loop array <a name="circularloop"></a>

```javascript
let myArray = ["red", "green", "blue"];
const text = document.getElementById("text");
let count = 0;

function cycleArray() {
  let index = count % myArray.length;
  text.style.color = myArray[index];
  count++;
}

setInterval(cycleArray, 1000);
```

# Promise <a name="promise"></a>

```javascript
let p = new Promise((resolve, reject) => {
  console.log("promise is pending");
  setTimeout(() => {
    reject("nhi hua");
  }, 5000);
});

let t = new Promise((resolve, reject) => {
  console.log("promise is pending");
  setTimeout(() => {
    resolve("ho gaya");
  }, 5000);
});

t.then((v) => {
  console.log(v);
}).catch((e) => {
  console.log(e);
});

p.catch((e) => {
  console.log(e);
});
console.log(p);
```

# Promise Chaining <a name="jsobjects"></a>

```javascript
let p1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Value 1");
  }, 11000);
});

let p2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    // resolve("Value 2")
    reject("Value 2");
  }, 2000);
});

let p3 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Value 3");
  }, 3000);
});

let promise_all = Promise.all([p1, p2, p3]); //all promise value
let promise_all = Promise.allSettled([p1, p2, p3]); //all full filed value
let promise_all = Promise.race([p1, p2, p3]); // first fastest value
let promise_all = Promise.any([p1, p2, p3]); // first full filed value

promise_all.then((v) => {
  console.log(v);
});

p1.then((v) => {
  console.log(v);
});

p2.then((v) => {
  console.log(v);
});

p3.then((v) => {
  console.log(v);
});
```

# Nodejs With Sqlite <a name="nodesqlite"></a>

```javascript
const express = require("express");
const bodyParser = require("body-parser");
const sqlite = require("sqlite3");
const cors = require("cors");
const db = new sqlite.Database("./Library.db", sqlite.OPEN_READWRITE, (err) => {
  if (err) return console.error(err);
}); // Create Library.db file first
let sql;
const app = express();
app.use(bodyParser.json());
app.use(cors());

app.post("/addbooks", (req, res) => {
  sql = "INSERT INTO book(name) VALUES (?)";
  try {
    console.log(req.body);
    const { name } = req.body;
    db.run(sql, [name], (err) => {
      if (err)
        return res.json({
          success: false,
        });
      console.log("inserted " + name);
    });
    return res.json({
      success: true,
    });
  } catch (error) {
    return res.json({
      success: false,
    });
  }
});

app.get("/books", (req, res) => {
  sql = "SELECT * FROM book";
  try {
    db.all(sql, [], (err, rows) => {
      if (err) return res.json({ success: false });
      if (rows < 1) return res.json({ success: false, error: "No match" });
      return res.json(rows);
    });
  } catch (error) {
    return res.json({
      success: false,
    });
  }
});

app.listen(5000); // run on localhost:5000
```

# Upload file via API <a name="fileuploadviaapi"></a>

```jsx

  const [ImageUpload, setImageUpload] = useState("");
  const [name, setName] = useState("");

  const uploadFile = async () => {
    if (ImageUpload === "") return;
    let bodyContent = new FormData();
    bodyContent.append("name", name);
    bodyContent.append("field", ImageUpload);

    let response = await fetch("http://127.0.0.1:8090/api/collections/images/records", {
      method: "POST",
      body: bodyContent,
    });

    let data = await response.text();
    console.log(data);
    alert("File Uploaded");
  }




return{
<input type="text" placeholder="name" onChange={(e) => setName(e.target.value)} value={name} />
<input type="file" onChange={(event) => { setImageUpload(event.target.files[0]); }} />
<button onClick={uploadFile}> Upload Image</button>
}
```

# get Input in react <a name="inputinreact"></a>

```jsx
const [name, setName] = useState("");

return{
  <input type="text" placeholder="name" onChange={(e) => setName(e.target.value)} value={name} />
}

```

# Use context <a name="usecontext"></a>

### cartcontext.js

```jsx
import { createContext } from "react";

const cartContext = createContext();

export default cartContext;
```

### cartstate.js

```jsx
import { useState } from "react";
import cartContext from "./CartContext";

const Cartstate = (props) => {
  const [cart, setCart] = useState([]);
  const update = () => {
    setCart(JSON.parse(localStorage.getItem("cart")));
  };
  const EmptyCart = () => {
    localStorage.removeItem("cart");
    setCart([]);
  };
  const updateOnline = () => {
    const cartId = localStorage.getItem("cart_id");
  };

  return (
    <cartContext.Provider value={{ cart, update, EmptyCart }}>
      {props.children}
    </cartContext.Provider>
  );
};

export default Cartstate;
```

### app.js

```jsx
function App() {
  return (
    <div className="App">
      <Cartstate>

          // inside all data

      </Cartstate>
    </div>
  );
```
