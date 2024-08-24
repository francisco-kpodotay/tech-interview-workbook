# Web Module Questions

## Modern JS

What is ECMAScript? What is the difference between Javascript & ECMAScript?
  - Ecmascript is a standard between scripting languages like javascript, jscript, typescript. It is a standard to ensure that the different scripting languages works well in the browsers and on the web. (ECMA-262)
  Ecmascript represents ascripting language specification, it provides the rules and gidelines for a scripting language

  - The difference between is ecmascript is set of rules, guide lines and javascript is a language that is based on the ecma's rules and guide lines
  (With ecma you can learn how to create a scripting language and with javascript you can learn how to use that spacific scripting language)

Explain the concept of "block scoping" introduced in ES6. How does it differ from function scoping?
  - Block scope means that a variable is only accesable inside of the block of which is created in (inside the cury braces {}).
  Examples for block scopes are if else statements, loops
  - Function scope means that a variable is only accesable anywhere inside a specific function, but only that function and the variables are called local variables. The difference between the block and function scope is use its use case, function scope used for functions and block scope is used in if statements and loops and in block scope if you want a variable to be avaible you have to make an object for it.

What are template literals in ES6 and how do they improve string manipulation in JavaScript?
  - Template literals are a new method to build strings in javascript which came with ES6.
  - It uses a backtick caracter (``) to generate a string and you can use the ${} simbol to pass any variable or values to appear inside the string
  - It is usefull, because we don't have to concatanate strings or other values together to represent a text

Explain the concept of "destructuring assignment" in ES6. How does it simplify variable assignment and object/array manipulation.
  - With destructuring you can take out, unpack values from arrays or properties from objects
  - With this you don't have to create a separate variable with a different name, you can use the destructoring method to get a value from an array and you don't need to use the index, also you can assign a variable with a value of a property from an object relatively easly
  ```js
  const obj = {name: 'Wayne', age: 32}
  const {name} = obj; ===> 'Wayne'
  
  const arr = [1,2,3];
  const [frist] = arr; ===> 1
  ```

What is the "spread operator" in ES6 and how can it be used to manipulate arrays and objects more effectively?
  - With the spread operator you can make a shallow copy of an object or array (imutable variables);
  - You can use it to don't modify the original data or tho have a copy of it
  - With arrays you can copy the content of the array inside a new array (You don't have to concat)
  - With objects you can copy the keys and the values into another object
  - Be careful with 2d reference types, because it copies the pointer of the memory allocation

  ```js
  const arr = [4, 5, 6];
  const newArr = [1, 2, 3, ...arr] ===> [1, 2, 3, 4, 5, 6]

  const obj = {name: 'Jenifer', age: 27}
  const data = {people: ...obj} ===> {people: {name: 'Jenifer', age: 27}}
  ```

How does ES6 introduce the concept of "default function parameters"? Provide an example of using default parameters in a function.
  - With default parameters you can set a default value of a parameter in a function, so if it doesn't provided with a argument the default value will bea assigned to the parameter
  - If the function has an argument than the passed value will be assigned and the default will be cancelled
  - It is usefull to have less errors in our code

  ```js
  function greeting(name = 'User'){
      console.log(`Welcome ${name}!`)
   }
  greeting(); //'Welcome User!';
  greeting('Clark'); //'Welcome Clark!'
  ```

Explain the concept of "modules" introduced in ES6. How do they improve code organization and reusability in JavaScript?
  - Modules are representing files, most commonly scripts. Modules can load each other and also use eachother as well. You can export and import each modules
  - The benefits of modules is that you can use both on the client and on the server side as well, because browsers supperted
  - With modules you get a lot of core features like strickt mode, module level scoping (You can only access exported values), evaluation (Only loads once, when it starts)
  - Modules usefull when you creating a large application an you want to separate to smaller parts and also if you want to import some else's code you can easly import them and use them (It is important with frameworks and libaries)

Compare the CommonJS and ES6 "modules". What are the differences?
  - Node js supports CommonJS modules (require, module.export), but in the later versions it introduced the ES6 modules
  - Browsers and client side applications supports the ES6 modules by default (only this)
  - Differences:   
    - CommonJS loads synchronously while ES6 loads asynchronously
    - ES6 syntax are easier to read than CommonJS
    - CommonJS are the default for node js, with ES6 you have to change the type to modules
    - ES6 modules are newer than CommonJS modules
    - CommonJS is more flexible than ES6

What are higher-order functions in JavaScript?
  - Higher order functions are functions thats takes callback functions as parameters
  - The most common higher order functions: map, filter, reduce, addEventListener, foreach, (promisses)

Explain the purpose and functionality of the map function in JavaScript. How does it differ from the filter and reduce functions?
  - With the map function you can go through an array and modify each item. It's returns an array with the modified values inside. It takes a callback function as parameter and will run the function on every element
  - It is different than filter and reduce, because it will return with the same amount of elements that it started with. So if an array consist of 6 elements it will return with 6 modified elements

How can the filter function be used to selectively extract elements from an array based on a given condition? Provide an example where the filter function is used to create a new array with only the elements that meet the specified criteria.
  - If we privde a condition where we want to return the opposite of what we searching for. For example we want to remove the number 3 from an array. Our condition would be to retur those values that are not eaqual to 3.
  ```js
  const arr = [1,2,3,4,5,6];
  const filteredArr = arr.filter(num => num !== 3); // [1,2,4,5,6]
  ```

What is the role of the reduce function in JavaScript? How can it be used to aggregate or combine the elements of an array into a single value? Provide an example where the reduce function is used to calculate a cumulative sum or find the maximum value in an array.
  - The use for the reduce function is to simplify operations with arrays. We can use the reduce to sum all the numbers of an array or to reduce the elements to one value
  - Reduce function uses an array, a callback function, and a initial value. Reduce will return with one value (initial value), the callback function takes two parameters a accumulator and a current value too. Its modifies the current value with operation thats inside of the callback function.
  ```js
  const arr1 = [1,2,3,4];
  const sum = arr1.reduce((num, curNum) => num += curNum, 0); ===> 10
  ```

## Fetch

How does a query string parameter in a URL contribute to web application functionality? Explain how query string parameters are typically used to pass data between web pages or APIs.
  - Query string are helpfull to get a special data or limit the number of data that an api gives back to us.
  - With query string parameters you can filter throug a large amount of items and limit them by the query parameters, alos you can chan together multiple query parameters.
  - In most cases the query parameters are written after the path url, it gets separated with a question mark and you can give them the name of that specific query (key) and after an equal sign you can give the value that you want to search for. Not every api uses query parameters, so read the documentation on how to use the query parameters of that specific api

  [Example url](http://some.com/api/something?height=5&width=7)

What is the purpose and functionality of the fetch function in JavaScript?
  - The purpose of the fetch function is to get, post, modify and delete information from a server without reloading the whole page.
  - The most common use cases of the fetch is to get data from a server of database and modifying the page without reloading.
  - Also you can use the fetch function to update, delete, modify data (CRUD)
  - The fetch is an asycromuos operation

Explain the syntax of the fetch function and how it handles asynchronous operations. Compare and contrast the syntax of making HTTP requests using fetch with async/await versus the syntax using .then() and .catch(). What are the key differences and benefits of using the async/await syntax in terms of code structure and readability?
  - The fetch function have two syntax 
  - One is with then 
    - This was the first version of the fetch function and it uses promisses to get the data
    - At first you have to send the fetch request, after that you have to use the .then() with a callback fucntion to get the data. You will use the callback's parameter to access the data (previous callback returned value). The data will be only avaible in the specific callback function, because it uses the function scope of the callback and you have to write the rest of your code in the callback, and chane together these blocks
    - This leads to readability issues and it introduced the "callback hell".
    - Also you can use some other functions like finally and catch to handle errors or other activities
  ```js
  function fetchCaracter(){
    fetch("http://127.0.0.1:3000/api/people/1")
    .then(res => res.json())
    .then(res => console.log(res)) // {name: 'Tony Stark', age: 38, isFictional: true}
    .catch(err => console.log(err));
  }
  ```

  - The other way is the asyn/await mehod
    - This is the newer version of the fetch
    - It still uses promisses, but in a different way
    - With this you have to creat an async function which will let you use the await keyword
    - Instead of then we uses await to wait the data to be fatched 
    - This method is more readable and cleaner than the .then() method and simplifies code and less prenoun to bugs
    - Also in this way you can store the data in a variable
  ```js
  async function fetchCaracter(){
    const data = await fetch("http://127.0.0.1:3000/api/people/2");
    const character = await data.json();
    console.log(character) // {name: 'Bruce Wayne', age: 30, isFictional: true}
  }
  ```

What is asynchronicity in JavaScript? Name some typical use cases when asynchronicity is needed.
  - Asynchronicity in javascript means that a particular task will be set aside untill it finishes the operations and let other functions to run while it's working and when it is finished it will return with the result that it created
  - It helps to keep the flow of the code clean and with this we don't have to rerender the whole page every time
  - Common use cases with asynchronicity: 
    - fetch functions
    - setTimeOuts, setIntervall
    - Reading and writeing files
                        
How can you handle the response received from a fetch request?
  - You can handle responses with inside the .then() blocks as parameters and sending down to another than or you can use the async function to get the value with the await keyword and asign to a variable inside the function.
  - In both ways you have to use the .json() method to get back the response's body.

How does the fetch function handle errors and handle HTTP status codes? Provide an example of using fetch to handle different types of responses, including successful and error responses.
  - You can handle errors with a catch block or the try catch block and you can log out the error or do other things
  - Javascript will throw an error if something wrong with the fetch
  - It predicts where the issues might be and tries to explain the problem
  - Also it uses the network tab on your browser where you can detect what is the ussue more in depth. Here you can check the request headers, body and method and the response's body, headers, method
  - Js will throw and status where you can see what is the problem
  - The statuscode is a great indicator of what is the issue
    - 200 level ===> everything ok
    - 400 level ===> something wrong with the request, request url or it's path
    - 500 level ===> server problems
        
Explain the parts of an URL.
  - Scheme/protocpll: Tells the web servers what protocol should use when someone accesses the webpage
  - Domain: Thels the browsor what specific webpage should it serve, or tells the browser on where can it be accessed
  - Port: Tells the browser on which port shold be openned and accessed by
  - Path: Specifies the location of a resource that the user want to access
  - Query parameter: The specific value that we searched on and asking the server to give these type of datas. This section starts with a questionmark and has a key where we can set the value for that key with an equal sign. Also we can put more query parameters togehter with the & sign
  - Fregments: We use fragments when we want to locate some content on the page

## Serve

Explain the concept of client-server communication in the context of web development. How does information flow between the client and the server in a typical client-server architecture?
  - The client is what we see in the browse and the server is what sends the resources and processing the data to the client.
  - The have to communicate with each other to create a dinamic website whit changing datas and with multiple pages
  - First the client sends a request to the server and it the request is valid than the server sends a response back to the client
  - This exchange of messaging the concept of server and client communication
  - To communicate they have to common language what they communicate on and it must follow some rules
  - This language is HTTP protocol

What is the role of HTTP requests and responses in web development? Explain the structure of an HTTP request and an HTTP response.
  - The HTTP is the language, protocolor interface on what the backend and the frontend communicates with each other
  - The structure of the http request: 
    - The first part of an http reques is the method and the path to where to send
    - The second part is the http headers where we can set informations about the request like content-type, host. content length
    - Lastly we can send the body that we want to forward to the server (You should only send request body, when you update(PUT/PATCH), create(POST) or delete(DELETE) data)
    
    - GET request:

      GET /docs/tutorials/linux/shellscripts/howto.html HTTP/1.1<br>
      Host: Linode.com<br>
      User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.1.8) Gecko/20091102 Firefox/3.5.5<br>
      Accept: text/html,application/xhtml+xml,<br>
      Accept-Language: en-us<br>
      Accept-Encoding: gzip,deflate<br>
      Accept-Charset: ISO-8859-1,utf-8<br>
      Cache-Control: no-cache<br>

  - The structure of the http response is similar to the request: 
    - The first is the method, path and also the status and statuscode
    - The second path is the http response headers where we also can set the respon's status, statuscode, content-type and some other key informations
    - Lastly the body what the server send to the client (Mostly we only have to send the response body on get requests and on the other cases we only sending status updates and re fetching the data)

Explain the key differences between the CommonJS require syntax and the ECMAScript (ES) module syntax import. How do these two approaches handle module dependencies and exports in JavaScript?
  - CommonJS uses the require keyword and to import files (modules) and uses module.export to export cedes
    - It load with syncronuosly
    - It is the default method to import codes
    - It is older and more flexible

  - The ES modules uses the import and export (default) keyword to share code with eachothers
    - Modules are files that can be shared between code bases
    - ES modules gives modular scoping and other features
    - It uses asyncronuosly to import and export data from a file
    - It is newer and more used novadays
    - It has a much easier syntax thancommonJS
    - It is supported both on the client and server side
    - You have to change the type to module to use it on the server

What are the advantages of using the ES module syntax import over the CommonJS require syntax?
  - The ES modules uses the import and export (default) keyword to share code with eachothers
  - Modules are files that can be shared between code bases
  - ES modules gives modular scoping and other features
  - It uses asyncronuosly to import and export data from a file
  - It is newer and more used novadays
  - It has a much easier syntax than commonJS
  - It is supported both on the client and server side

What is Express.js and how does it simplify web application development in Node.js? Explain the core features and benefits of using Express.js as a web framework.
  - Express is a backend applicatoion framework for node js
  - Express simplifies the development with it's easy to use syntax, error handling, custimazibility, high preformance and large community
  - Express proviedes features like routing capabilities, middleware functionalities, easy api development, integratable JSON authentication

Explain the process of handling static files (e.g., CSS, images) in Express.js. How can you configure Express.js to serve static assets from a specific directory in your application?
  - First we have to create a server that listens on a port and you haveto create a middleware for the static assets
  - After that we can use the built in use function which is runs between the time the server gets the request and the time the server sends the request out
  - In the use we have to give the endpont's name and use the built in express.static function to give the location of the files
  ```js
  app.use('/pub', express.static(path.join(__dirname, 'client', 'public')));
  ```

How does Express.js handle HTTP request/response cycles? Explain the process of receiving and responding to requests using Express.js middleware and route handlers.
  - Express uses there built in methods to handle responses and requests. In these methods we define a midleware which accepts reqest and response objects. The req and res objects are going through the middleware stack, which means that in every middlleware ending there is the next() function which passing the objects to the next middleware. If a middleware have a res.send() method at the end it will return the object to the client and finishes the cycle. So if we don't use the send method we passing to the next middleware in line or if we don't handle it it will stuck.
  - Middlewares stacks are starting from the top of the code and going downvard
  - Middlewares are running during the when the request has been sent and before response has ben sent
  - With expresses built in methods we can tell on what kind of request do we want to receive and on which "line" or route.
  - After this we can create our middleware which do some operations before we sand anything back to the client
  - After the process is finished we can send the data back to the client with the res object's send method
  - On the client side we can get the server's response with the then method or the async/await method

  - Server:
    ```js
      app.get('/api/test', (req, res) => {
        const num = req.body;
        res.send({multiplied: num * 2});
      })
    ```
  - Client: 
    ```js
      fethc('http://localhost:3000/api/test')
        .then(res => res.json())
        .then(data => console.log(data))
        .cathc(err => console.log(err));
    ```

## Forms

How does routing work in Express.js? Explain how to define routes and handle different HTTP methods (GET, POST, etc.) in an Express.js application.
  - Routing defines how an application reacts to a request to a particular endpoint (URI/path + the method). each route can have one or more handle function for a specific route
  - To define routes you have to decide what that specific rout will do and on which page will do it. For example if you want to create a route to serve the users page on a website you can use the get method with the '/users' route. If you want to send the users informations' from the database you can use a GET method with the '/api/users' endpoint to get some json data back. If you want to creat a new user you can use the POST method with the '/api/users' endpoint
  - You can handle the request with the express built in methods: 
    - .get()    ---> to send data
    - .post()   ---> to create new data
    - .put()    ---> to replace an existing data with a new one (update with replacing)
    - .patch()  ---> to update an existing data's value with a new value
    - .delete() ---> to delete a data









Eddig van formázva a file!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!













What are the various methods available in Express.js for sending responses to clients? Explain the differences between res.send() and res.json[] in Express.js.
  - The methods to send to the client: 
    - res.send()
    - res.sendFile()
    - res.sendStatus()
    - res.json()
  - Whit res.send() we can send any javascript type of data back to the client, but with res.json() we only can send json type to the client (JSON.stringify-ed data)

Explain what the express.json() middleware does?
  - It is used to parse incomming JSON data from an HTTP request and with this we can access the request's body parameter. Basically it is a built in bodyParser function get parse the JSON's body to an object

What is the purpose of the next() function in Express.js middleware? How can you use it to pass control to the next middleware function in the chain or to terminate the middleware processing?
  - When the next function is used in the route the middleware stack jumps to the next middleware in line and gives the controll th the new midleware
  - If middleware cycle doest end it will automatically call the next function
  - We can use it in authentication systems if the user's password is correct than use the next function, or if we run a code that needs to be terminated. For example if the timer is 0 than go to the next midleware in the line

Explain the concept of route parameters in Express.js. How can you extract dynamic values from the URL path using route parameters, and how are these values accessed within route handlers?
  - Route parameters are used to capture the values specified at their position in the URL. The captured values are populated in the req.params object's, with the name of the rout parameter as a key in the object.
  ```js
  app.post('/example/:id', (req, res) => {
    const parameter = req.params.id; // this will be the dinamic id
  })
  ```

Can you name some typical HTTP response codes and their meaning?
  - 200 level: Successfull responses
    - 200 (OK): request succeded
    - 201 (Created): request was succesfull and a new element created
    - 205 (reset): Tells that the document has to be reset in this path
  - 300 level: Redirection messages
    - 301 (Moved permanently): The URL of the resource has ben changed
  - 400 level: Client error messages
    - 400 (Bad request): The server cannot serve the resource, becouse something went wrong on the client side (Bad url, misspelled url)
    - 401 (Unathorized): The client have to authenticate itself
    - 404 (Not found): The server can't find the resource, or the url is unrecognizible for the server
  - 500 level: Server error responses:
    - 500 (Internal server error): The server can't handle a process or it crashed
    - 501 (Not implemented): The request method is not supported by the server and can't be processed
    - 503 (Service unavaible): The server is not ready to handle the request, because of the downtime or under maintenance 

Can you name some typical HTTP request/response headers and their meaning?
  - Content-type: It sets the type of the request, in default it sends html file, but you can set to JSON, javascript, css to be recongnizible for the browser
  - Host: It specifies the host name and port number of the server
  - Location: It indicates the URL to redirect a apge to. We use this header when the status code is in the 300 level or if it is 201
  - Date: It contains the date and time when the request is created at
  - Server: It describes the origin's software that used to handle the requests
  - User-Agent: It lest the servers know on which browser the request from or the operating systems 

What are the common HTTP methods used in web development, and what are their respective purposes?
  - GET: We use this when we want to get reource from the server
  - POST: We use this when we want to send information to the server (Post a new data on the server)
  - PUT: We use this when we want to update an informatio, but we replacing the old one with the new one
  - PATCH: We also update the data with this, but we don't replace it, we just changing some of there parameters (Patching them)
  - DELETE: We use this when we want to delete information from our database


How does the GET method differ from the POST method? Explain when it is appropriate to use each method. Which one uses request body to send data? What the other method uses to send data?
  - With the GET method we usually requireing information from the server. We don't put anything to the body part and we only setting the method to GET. We use this method when we want to grab a html or when we want to display information on the client side from the server. The server sends some information back to the client side
  - With the POST request we usually sending information to the server to be processed. We have to set some header information for this process, most knowtably the request method, the content-type on what type of data we want to send, and this method has a body part, where we can define the data that we want to sent to the server. For example for this is when we create a new user, or when we want to create anew entity, login, authentications to check if the data correct. The server don't have to send back any infromation, but it usefull to send some JSON object back

Explain the use of the PATCH method in HTTP. How does it differ from the PUT method, and when should it be used to update a resource?
  - The PATCH method applies partial fixes, updates, modification to an existing file
  - We use PATCH when we already have an entity and we just want to modify one of the parameters
  - With the PUT method we replacing the the existing resource with a new one, but with PATCH we don't replace it, we just modifie informations about the existing data
  - We should use it if we just want to change one thing about the data

How can the DELETE method be used to remove a resource from a server? Explain how the DELETE method works and any considerations for handling resource deletion.
  - We can use the DELETE method to do somthing when a delete request is sent from the client.
  - In the DELETE endpoint's midlleware we can handle the delete function
  - If we have a database easly search for the specific information with filtering and we can use the database's built in delete function
  - Or we can retreive all of the data and filter out the one instance that we want to delete with the filter fuction and save the new array
  - When a client sends a DELETE request it asks the server to remove the specific information from the database, it can be accessed in the request's body or in the url paramters/route parameters.
  - Now the server can specifie of the data and can handle the removal

How do you handle form submissions using JavaScript? Explain the process of capturing form data and preventing the default form submission behavior.

  - To handle form submittion we can set an eventListener on the form element and we can specify what to do when the form is submitted in the callback function
  - The callback function takes a event parameter where we can acess information of the event that happened
  - In the submitHandler function we can prevent the default behaviour of the form with the event.preventDefault()
  - To capture the information of the inputs we can use id's (not the correct way), but the most practical way is to use the inputs name attribute
  - We can referenc to the element that the event is happened on with the event.target key
  - When we have the targetted element we can access it's parameters, so we can access by there name
  - When we have the selected inputfield we can get there values with the value key
  - After that we can send it to server in request body

  ```js
  const form = document.querySelector('#form');

  form.addEventListener('submit', (event) => {
    const user = {
        name: event.target.elements.name.value,
        age: Number(event.target.elements.age.value),
    }

    fethc('/api/test', {
        method: 'POST',
        headers: {
            'Content-type': 'application/json'
        },
        body: JSON.stringify(user)
    });
  })
  ```

Explain the required elements necessary to define a form in HTML.
  - From tag: this is like a container of the form elements and activates the from behaviour
  - Label: here you can ad some text to describe the input field 
  - Input field: This is where the user can write the data in. The input filds can be different type, it can be text, checkboxes, radio buttons. Also you can specify the text's type to be number, email, password or even date
  - Textarea: This is like the input field, but it is larger and you can write multiline texts 
  - Submit button: This is required to send the data to the server. You can set the type to be submit button, but if you put a button in a form it automatically sets its type to be submit

  ```js
  <form>
    <label for="name">Name: </label>
    <input type="text" required maxlength="10" name="name" id="name"/>
    <br/>
    <label for="password">Password: </label>
    <input type="password" required minlength="8" name="password" id="password"/>
    <br/>
    <label for="guideLine">Do you agreing the guidelines? </label>
    <input type="checkbox" required name="guideLine" id="guideLine"/>
    <br/>
    <label>Online</label>
    <input type="radio" value="online" id="online" name="connectivity"/>
    <br/>
    <label>Offline</label>
    <input type="radio" value="offline" id="offline" name="connectivity">
    <br/>
    <button>Login</button>
  </form>
  ```

What is the purpose of the required attribute in HTML form elements? How does it enforce mandatory input fields and prevent form submission without the required information?
  - The required attribute's purpose in html is to prevent to submit the form if the inputfield is missing, so you have to fill out the input field
  - When the input is missing it shows an alerting text near to the required field and the form controll will stop and don't send the form to the server

Explain the different types of form input fields available in HTML. How do input types like text, number, email, checkbox, and radio buttons differ, and how are they used in forms?
  - text: This is the most common, with this you can type visible text, usually we use it for names and usernames
  - password: This will replace the regular caracters (UTF-8) to * to hide the text that has been entered in the field
  - number: This will only accept number types of data and it has a up and down button in the field. It will alert if incorrect
  - email: This will only accepts email strings. It checks if the string has the @ symbol and the .com in the end. This also alerts if it is incorrect
  - checkbox: This will turn the input filed to a checkbox which you can check. It will have the attribute of checked, it will return true or false
  - radio: This will turn to a radio button on which you can activate or unactivate if ther are more of them and set there values
  - date: This will accepts date values that is separated with - , if you want to change it will show a calender to select the value
  - file: With this you can select a file from your file system
  - color: With this you can select a prefered color
  - range: With this you can create a slide, range to set the value, usually it will return number values between two numbers

Can you explain the purpose of the name attribute in a context of form submission?
  - The name attribute is used to specify an html element's name
  - You can use the name attribute to reference to the element in javascript
  - In the form context we use the name attributes to separate input fields to each other and get there values throuh them when we have a submit event
  - We can use the event's target values to get the specific name element


- Can you explain how we can connect a label tag to a form element?

    - We can connect a label to an input by using the labels for attribute
    - In the for attribute we have to give the specified input's id 

    e.g.: <label for="name">Name: </label>
          <input type="text" id="name" />




- How can you dynamically manipulate or modify form elements using JavaScript? Explain how to add or remove form fields dynamically based on user interaction or specific conditions.

    - You can create a simple function to listen for the dynamically changing data
    - The function vould take an array that contains the new form inputs name/label
    - We can easly go throug on the array and create inputs for the elements and appending them to the form


    e.g.:

    function changeform(inputFields){
        if(inputFields.length){
            const form = document.querySelector('#form');
            
            for(const inputField of inputFields){
                const input = `
                <label for="${inputField}">${inputField}</label>
                <input type="text" name="${inputField}" id="${inputField}">
                <br />
                `

                form.insertAdjacentHTML('beforeend', input);
            }
        }
        return
    }

- How can you convert form data into a format that can be easily transmitted or processed by the server?

    - You can easly translate the form data by creating an object and setting the keys to the specific input's name and assigning the value to it
    - After this you can use the JSON.stringify method to convert it to JSON type
    - And now you can send it to the server

## React

- What is React.js and what are its key features? 

    - React is a javascript framework and library
    - It is usefull, because it helps you building interactive web pages and helps you handle js event listenersa and dom manipulations farely easly
    - It is a frontend web framework
    - Key features: - JSX syntax
                    - Virtual DOM
                    - Components
                    - Conditional rendering
                    - Hooks

- Explain the concept of virtual DOM and how it contributes to React's performance.

    - The virtual DOM is a representation of the real DOM on a webpage and it synced together with eachother
    - The ReactDOM library syncing together the virtual dom with the real dom
    - This approach enables react to be a declarative language, which means that you must have to tell which state should the react framework use and it will set it to be
    - This helps a lot, because you don't have to make the DOM manipulation, rendering and event handling by your self and you can create web apps quicker


- Explain the component-based architecture in React.js. How do components work, and how can they be composed to build complex user interfaces?

    - In react we orgenisis our code in component, components means smaller functions that will return some JSX code
    - With this approach we can desegment our code to smaller parts and it would be easier to read, maintain and we can create reusable code
    - In components we can access other components, in this way we can create a large application from a smaller building blocks
    - In a example components are like lego pieces and we can put them together to create a large star destroyer
    - In the component based architect we have the main component the App and it can access a couple of other components, in the other components we also can access different components

    - Every component has ther own separate states and ther API's, with this approach we can take our code to smaller peaces    


- What is the significance of JSX in React.js? Explain how JSX combines HTML-like syntax with JavaScript code and how it is transpiled into regular JavaScript during the build process.

    - React uses JSX syntax to represent html like elements on the page.
    - JSX stand for Javascrpt XML
    - With this sintax we can combine html and javascript together and it adds a much more simplified sytax for developers and also enables dynemic rendering, conditional rendering, and to invoke function directly in JSX

    - In JSX you can combine html like syntax with javascript code with props, conditional rendering and states
    - If you use the curly braces {} in JSX it means that javascript code will be run inside of them and you can execute javascript code in that specified place of JSX
    - Also you can use javascript in the onEvent callers places

    - JSX is transpiled to vanilla javascript with a transpiler that is called Babel
    - Babel translate the JSX into javascript objects that the react framework can understand 
    - With this featurs we cat the declarative perspective of react js


- What are props in React and how are they used to pass data between components? Explain the concept of props and how they facilitate parent-child component communication.

    - Props are types of objects where the given component's, tag's values are stored
    - Props are shorthand for properties and they look similar to html attributes

    - Each component can access ther own properties with the prop keyword or object destructoring, when the are passed in the function as parameter
    - This will be an object that holds the given values and the keys will be the attribute's name
    - In this way we can sand data down to the cild components easly

    - With props we can create a parent child relation between components
    - We can send down some data to the child elements
    - Also we can sand data up to the parent element through function and the parent will decide what to do with that specific data
    - We also can send functions between components


- How can you access and utilize props within a functional component in React? Explain how to extract and use props using the destructuring syntax.

    - With the prop keyword or object destructoring, when the are passed in the function as parameter
    - If we use the props keyword we can referenc with the prop's name 
    - If we use the destructuring we have to do it on the parameter section and passing the properties name in a object

        e.g.: 

        function Login(props){
            
            return(
                <div>
                    <h1>{props.user}</h1>
                    <p>{props.email}</p>
                </div>
            )
        }


        function Login({user, email}){
            
            return(
                <div>
                    <h1>{user}</h1>
                    <p>{email}</p>
                </div>
            )
        }

- How can you pass callback functions as props in React? Provide an example of how to pass a function from a parent component to a child component, enabling the child to communicate with the parent.

    - If you want to pass a function as a props or if you want to pass data from the child to the parent element you have to send a callback function that will do the things that you want or which call another function
    - In this way you must use the on nameing convencion
    - Now you can send data to the parent component with the function's parameter

    e.g.:

    function App(){
        const [name, setName] = useState();

        function handleNameChange(event){
            setName(event.target.value);
        }

        return(
            <InputComponent onNameChange={(event) => {handleNameChange(event)}}/>
        )
    }


    function InputComponent({ onNameChange }){

        return(
            <input onChange={onNameChange}/>
        )
    }


    - With this example we setting the App's name state on change from the InputComponent component
    - The handleNameChange function can access the InputComponent's data when we setting as parameter


- Explain the concept of spreading props in React. How can the spread operator be used to pass multiple props from a parent component to a child component in a concise manner?

    - With spreading props in react we can simplify them
    - If we have our data/props in a jobject we can spread them in a component and the object's keys will be passed down to the components
    - Also we can also select special components that the component will consume
    - With the spread operator you can create a more usable interface for the component to talk with the parent component
    - With this method we can separate the first property from the rest, and also you can spread down the rest of the properties to other components
    - With this approach we can create dynamic and reusable components

    e.g.:

    function App(){
        const inputField = {
            label: 'eamil',
            type: 'email',
            placeHolder='Write your email!'
            required: 'required'
        }

        <InputField inputInfo = {inputField}/>
    }


    function InputField({ label, ...rest}){
        return (
            <form>
                <label>{label}</label>
                <input {...rest}/>
            </form>
        )
    }



- Explain the concept of default props (with ES6 JS syntax) in React. How can you define default values for props in a component to handle cases where the prop value is not explicitly passed?

    - Default props are used to set any prop's value wheter a the props value is set or not
    - It is usefull to handle errors and breaks in a situation where a user have to set a value, but it is not required
    - If the user doesn't set any value the default value will be used to further operations
    - You still can overwrite with other valies if it is passed in the props
    - To set the default props you can use the old method where in the bottom of the component you called the defaultProps method and set tha values in a object
    - But the newer and cleaner way we can set it in the parameters with destructoring

    e.g.old:

    function App(props){
        return(
            <div>
                {props.id}
            </div>
        )
    }

    App.defaultProps({
        id: 2
    })



    e.g.new: 

    function App({ id = 23}){
        return(
            <div>
                {id}
            </div>
        )
    }


- Explain the immutability principle when working with props and states in React. Why is it important to avoid directly modifying prop values within a component, and what are some best practices for maintaining immutability?

    - In react props and states are imutable, read only data
    - If you want to change them you have to use the setter function of the use state to change the value of a state
    - You can't assign a value directly to a state or props, because they won't do anything, thats why states have the setter function
    - React is built that you only can change the states value with there setter functions
    - Mutating state and props date can cause hard to solwe bugs and other optimization issues
    
    - Some of the best cases to prevent mutability is to create a variable where we can modify the current value of the state and set the variable as a new value in the setter function
    - The other best practice (My favourite) is to use the a callback in the setter function to access the previos value of a state (this is good if you want to modify data)

        e.g.: setUser(prev => ({
            ...prev,
            userName: 'OtherOne'
        }))


- How does React.js handle state management? Explain the concept of state and how it differs from props.

    - State management is a process for react to manage data that react components will need in order to render themselvs
    - This data is stored in the component's object
    - When the state object changes it will re render the component

    - States are variables that holds the initial values of a component
    - With state you can change the value of the variable with its setter funtion
    - Props are the set of attributes that we pass down to other components and can be accessed by them
    - Props are primarly used to communicate between two components and states are used to store data or use them in conditionals


- What are React hooks? Explain the purpose and benefits of hooks like useState, useEffect in React.js.

    - Hooks allow function components to have access to state and other React features
    - With hooks you don't need to use class components anymore
    - Hooks allow you access to React state and lifecycle features from function components

    - With the useState hook you can easly set values to a variable and change it later, also if you change the state hook the component will re render itself
    - With useEffect you can set a conditional for running a function when that conditional changes, if you give a empty array as conditional it will only run once
    - This helps the component to render when something changes and prevent unnecessary renders

    
- Explain the concept of virtual DOM reconciliation in React.js. How does React efficiently update and render components by performing minimal DOM manipulations?

    - When the react component changes duo to state or prop changes React doesn't immediatelly manipulates the real dom
    - First React checks the differences between the currant DOM and the updated DOM
    - If a change have been made React re-renders the Virtual DOM tree
    - After the changes detected Reacts updates the realDOM to

    - To effectively update and re-render components with minimal DOM manipulation React uses the Virtual DOM, which is shellow copy of the real dom
    - The real dom will only be changed when the current VDOM is different from the previous one



- Explain how to manage complex state objects with useState. Explain techniques like object spreading or merging to update specific properties within an object state.

    - In use state we can store any javascript values
    - When we updating the state we usually overwrite the previous value with anotherone ,there for it is hard to update object's parameters
    - Object spreading: 

        const newValue = {
            ...products,
            number: 5
        };

        setProducts(newValue);

    - In this example we created an object where we spread the previous values and in the and we overwrite one of them with the new value

        setProducts(prev => ({
            ...prev,
            number: 5
        }));

        - Also we can use it as a one liner

        


- Why is it important to provide a new array as an argument to the useState hook when adding an item to an existing array?

    - Because React state variables are unmutable
    - You can't assign values to a react state variables, you have to use the setter function
    - It is also needed to react to compare state changes and re-render the component when the state is changed


- How does conditional rendering work in React? Explain the different techniques and approaches available to conditionally render components or content based on certain conditions or state values.  How can it be used to control the visibility or behavior of components based on user interactions or other dynamic conditions?


    - You can use conditional rendering in react to dissplay different jsx element on a certain conditions (When a the state is changes or on a specific state value)

    - With this way you can create a interactive and dinamic component and pages
    

    Thecniques: 

    if(products){
        return (
            <>
                <h1>Products</h1>
                <Products />
            </>
        )
    } else{
        return <h1>Loading...</h1>
    }

    - This is a simple if else statement which will renders the element depending on the state

    return(
        <>
            {products && <Products />}
        </>
    )

    - The && syntax is only renders the Products component when the products state is not falsy (Only renders the component when the statement befeore the && is true or in the other case it will render null, nothing)


    return(
        <>
            {products ? <Products /> ? <h1>Loading...</h1>}
        </>
    )

    - The turnary operation is the shorthand way of an if else statement


- How can you create a select input element in React? How does it differ from the html's select tag? Can you show an example of a controlled and an uncontrolled select element with default value setting?

    - You can create a select input simulary to an html select input, but you can do a conditional rendering  with the {} brackets 
    - For example if you have an array of values you can render them in the options with the value from the array
    - Most of the react selects are controlled, also you can use the uncontrolled way too

    e.g.:

    const fruits = ['apple', 'banana', 'kiwi', 'orange'];
    const [selected, setSelected] = useState('Choose a value');

    return(
        <div>
            <select value={selected} onChange={(event) => setSelected(event.target.value)}>
                {fruits.map(fruit => <option value={fruit}>{fruit}</option>)}
            </select>
            <p>{selected}</p>
        </div>
    )
    


## Database

- What is MongoDB, and how does it differ from traditional relational databases? Explain the key features and advantages of MongoDB as a NoSQL database solution.

    - MongoDB is a NoSQL database management application
    - NoSQL database systems offer an alternative to traditional relational databases

    - In SQL data is stored in tables, rows and columns with relations between enteries
    - In MongoDB, the data is stored in documents using JSON-like structure

    - Benefits of using MongoDB: - flexible data store because of its JSON-like document format
                                 - document-based data model can represent hierarchical data structures
                                 - it is easly scalable and more avaible (horizental scaling)
                                 - easy to use syntax
                                 - accessability
                                 - cloud based service (atlas)



- Explain the concept of collections and documents in MongoDB? How does MongoDB store data, and how is it organized within collections and documents.

    - In MongoDB documents are individual records, the basic unit of data (One data from the database), usually documents consist key-value pairs, which is the basic unit of data. Documents can have different fields
    - Collection is a grouping of documents (tables in SQL). A collection exists in a single database

    - MongoDB stores data objects in collections and documents 

    - MongoDB is made up of 3 type of components: - Databases
                                                  - Collections
                                                  - Documents

    - The databse at the top level, colections at the next level and in the end there are the documents
    - Database provides a container for storing and organizing data

- What is Mongoose.js, and how does it simplify working with MongoDB in a Node.js environment? Explain the key features and benefits of using Mongoose.js.

    - Mongoose is an OBJ (Object Data Model) library
    - It manages relationships between data, provides schema validation, and is used to translate between objects in code and the representation of those objects in MongoDB

    - Mongoose provides an easier syntax than MongoDB and pre defined functions to make changes in the database and communicate with MongoDB
    - Mongoose also provides Schemas and models, for organising documents
    - Schemas are for creating the shape of the document and adding additional validations (schema validations) like reguired, type, min, max
    - Models are a higher-order constructors that take a schema and create an instance of a document

    

    

- How do you define and create schemas in Mongoose.js? Explain how schemas define the structure and validation rules for documents in MongoDB collections.

    - We define a Schema with a new keyword and the Schema class
    - In the constructor we create an object of the document, what fuilds it will use and the validations
    - After that we can export or create a variable where we can store the model
    - We can create a model with the model() class
    - In the constructor first parameter is the name of the collection your model is for, in the next parameter we pass the schema

    e.g.: 
    const dogSchema = new Schema({
        name: {type: String, required: true, min: 1, max: 200},
        age: Number
    })

    const Dog = model('Dog', dogSchema);

    - We can set some validations in the schema with assigning and object with the properties of the validation of a field
        
        name: {type: String, required: true, min: 1, max: 200}

- Explain the different types of Mongoose.js data modeling techniques. How can you define relationships between MongoDB collections using Mongoose.js, such as one-to-one, one-to-many, and many-to-many relationships?


    - Modelling techniques in mongoose :

    const dogSchema = new Schema({
        name: {type: String, required: true, min: 1, max: 200},
        age: Number
    })

    const Dog = model('Dog', dogSchema);

    ######

    const dogSchema = new Schema({
        name: {type: String, required: true, min: 1, max: 200},
        age: Number
    })

    export default model('Dog', dogSchema);

    - In mongoose you can create relations between collections with the ref property
    - The ref is for referencing another document from another collection or Schema
    - We usually store the id's of a shcema in the ref property 
    - If we want to fill out the the property with the related schema's data we have to use the populate function

    e.g.:

    const userSchema = new Schema({
        userName: {type: String, required: true, max: 2, min: 300},
        email: {type: String, required: true},
        toDos: [{
            type: Schema.Types.ObjectId,
            ref: 'Todos'
        }]
    })


    const toDoSchema = new Schema({
        title: String,
        comment: String, 
        createdAt: Date,
        ends: Date,
        ref: {
            type: Schema.Types.ObjectId,
            ref: 'Users'
            required: true
        }
    })


- What are the available options for querying and manipulating data using Mongoose.js? Explain how to perform CRUD operations (create, read, update, delete) using Mongoose.js methods and queries.

    - In Mongoosejs you have query functions that can make your job easier to get documents, also you can write your own query to get specific elements
    - You can use both way to query a document from the collection
    - If you use your own queries you have to get all of the documents from the collection and after that you can perfoem the queries on it
    - You can write your own query after the where() function which accepts the field that you want to filter by

    - Own queries: const largerThan = await User.find({}).where('age').lg(20).sort({userName: -1}).limit(5)
        // In this example we filter out the documents where the age is larger than 20 and sort them in desc way and limit the output to 5 documents


    - You can perform CRUD operations easly with the bult in functions

        - Create: create, save
        - Read: find, findOne, findById
        - Update: updateOne, updateMany, findOneAndUpdate, findManyAndUpdate, findByIdAndUpdate
        - Delte: deleteOne, deleteMany, findByIdAndDelete, findOneAndDelete, findManyAndDelete


- Explain the process of connecting to a MongoDB database using Mongoose.js. How can you configure and establish a connection to a MongoDB server using Mongoose.js in a Node.js application?

    - To connect to MongoDB with Mongoosejs you have to install mongoose
    - You have to create a new project in MongoDB and a new Database
    - When you create database you can add members and you can add your ip address to only be accessed by that ip address
    - Also in this place you can create a password for the database
    - When the database is ready you can copy the connection string
    - In the connection string you have to replace your password
    
    - In Mongoose we have a built in constructor the .connect which takes the connection string
    - In this way we can connect to the databese relatively easly

    e.g: Mongoose.connect('<Connecton string>');

    - To establish a good connection and prevent buffer errors you can await it or you can use the then method

## MERN

- Explain the concept of React Router. How does it enable client-side routing in React.js applications and facilitate the creation of multi-page-like experiences?

    - React router is a third party react library which can make your react application routable on the client side
    - With react router you can have specific paths and if the url changes then the specific page will load in (component)
    - React router relies on the url, when the url changes it will check the routes and refress the components
    - It don't send the request to the server, React router will manage the urls and the re-rendering of the page
    - It stores the pages in it history so you can go back to the previos page too or on the next page
    - Also because it doesn't forward request to the server it is faster and became one of the most fommon libraries for one page applications
    - React outer firtst update the url and it triggers a re-rendering in the page or components


- Explain the concept of server-side routing in Express.js. How does Express handle incoming requests and route them to the appropriate API endpoints or route handlers?

    - First the client sends and HTTP request for the server and the server will receive the HTTP request and looks for the method and the and triest to find the correct path for the request
    - If the path and the method was correct then the express will use some middleware to process the information and sends respons back
    - If the path or the method was incorrect than it will send a 500 server error

    - In express it will go from the top to the bottom when it searches for the request
    - Express methods: POST, GET, PATCH, PUT, DELETE



- What is the MERN stack? Explain the individual components of the MERN stack and their role in building web applications.

    - MERN means: MongoDB, Express js, React js, Node js
    - These are technologies that can create a full-stack application easly
    - We call them tech stack

    - MongoDB is used for our database, it is for managing our data in a correct form
    - Express js is for our backend, it is for handeling requests and sending responses, resources and also for processing data and filtering. After these we send back the response to the client side

    - React js is for our frontend, it is for represent the information on the webpage and creating a UI, interface for the client
    - Node js is for running the server and the client side. This is server side javascript environment with built in npm (node package managger)


- Explain how does a proxy works during React development. How can you tell the webpack dev server to proxy the requests to your backend? What kind of URLs you have to use in the fetch in your JS code, if you want to use the proxy.

    - In the development environment we create a development server and the built in browswer functions doesn't allow us to send request to a server, which is running on a different port than the client side
    - For this reson we have to use proxy to don't get any CORS errors
    - Proxirs will send the request to the developer server then the developer server will send it to the server, so its seems like it from the same origin and same port
    - To configur the proxy we have to do it inside the package.json file and we have to add the location of the server to know where to forward the requests, also we have to give a name to it that we can use in our fetching
    - When we set the proxy don't fetch the servers location anymore insted we are using the uri  that we set in the prox

    e.g.:

        //package.json
        "proxy": "http://localhost:3000"


        //app.jsx

        useEffect(() => {
            const fetchData = async () => {
                const response = await fetch('/api/users');     <-- We are using the proxy's path to forward it to the server
                const users = await response.json()
            }
            fetchData();
        }, [])


        
- Explain the advantages and benefits of using the MERN stack for web development. How does each component of the MERN stack contribute to the development process and overall efficiency of building modern web applications?

    - The advantage of using MERN stack is that every technology is relies on javascript
    - It is simple to use them with each other because all of them are using javascript
    - Javascript is a farely easly learnable language
    - You can create quite big applications really quickly

    - Mongo DB: it is managging the data, it is a database application
    - Express: it is our server it is managing the requests and responses and sending the resources
    - React: it is our frontend, You can create the UI farely easly with it
    - Node: it is the server side javascript engine this is the base of our application it is like a kerne
    
- How does data flow in the MERN stack architecture? Explain how the frontend, built with React.js, communicates with the backend, developed with Node.js and Express.js, to handle client requests and serve data from the MongoDB database.

    - First the client (React) sends a request to the server with the built in fetch api
    - The server processes the request and then it sends a query to the database
    - The database sends the documents to the server
    - The server do some processing on the data
    - After that the server sends back the data to the client
    - The client will render the information on the UI