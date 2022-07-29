# JS-Interview-Questions
making a repo of interview JS question-answers for myself

# 1. Give a brief about JS.
A. Javascript, created by Brenden Eich in 1995, is one of the most widely used web development languages. It was originally created for the browsers to make dynamic web pages. However, now JS has become a lot more powerful because now it can be run on server and thus on any device which has the JS Engine installed making it a language of the FE as well as the BE.  

# 2. What is IIFE?
A. IIFE stands for Immediately Invoked Function Expression. As the name suggest, IIFE is a function in Javascript that runs as soon as it is defined. Any IIFE, the epression has two majpr parts:
The first part is an anonymous function i.e. a function without a name, ecnclosed inside of a pair of parenthesis. Whenever the JS engine sees the word 'funtion' it assumes that we're declaring a function and thus it expects a function name because by the syntax of declaring a function in JS, it has to have a name. And so without these first set of parenthesis, the compiler would throw an error. Thus we add this first set of paremthesis to let the compiler know that its not a function declaration but a function exprssion.
The second set of parenthesis again make sense because in JS to invoke a function, we have to use parenthesis after it name..so that's what the second set of parethesis is doing..its invoking the function that we just declared.

#  What is the difference between a function declaration and a function expression?
A. The main difference between a function declaraation and a function expression is that the function name can be omitted in case of function expression to create anonymous functions but not in case of declaration.
We can use function declarations for eg in the global scope and make it available throughout the code. If we dont want that, if we for eg want to limit the availablity of the function, we can use function expresson.
Another difference is that function declarations are hoisted while function expressions are not.
so for eg: printName()
function printName ( ) { }
will not throw any error
but
printName()
const printName = () => {}
will throw an error (printName is not a function in case of var, not defined in case of let and const)

# 3. What is an Object is JS?
A. JS has two types of data types, namely primitives and non-primitives. Primitive data types can hold a single value at a time. However, if we want to store multiple and more compelx data in a variable, we can use non-primitives, more commonly known as Objects. So Objects in JS are standalone entity which has properties and methods of its own. 

# 4. Create a user object with name and id properties and how to access the value of name property.
A.
         var user = {
            id: 1,
            name: 'Nikhat'
         }
         
    Accessing the value of the property using the dot operator like this: 
      user.name
   
# 5. Create an object with a method inside of it.
A. To declare methods inside of objects in JS, we need to first create a property with the same name as that of the method and then declare the method. For eg:
      
      function obj(id, name) {
            this.id = id;
            this.name = name;

            this.changeName = changeName;

            function changeName(newName) {
              this.name = newName;
            }
      }
   
   var obj1 = new obj(1, 'Nikhat');
   obj1.changeName('Shaikh');
   
# 6. What is scope and scope chain?
A. Scope is JS refers to the accessibility or visibility of variables i.e. which part of the prgram has access to which varibales.
   The main benefit of scope is security. By making certai varibales accessible only in a certain area of the code, we can avoid unintended modifcations to the variables from other parts of the code.
   Types of Scope:
   There are three types of scope. The global scope, local scope also called function scope and the Block scope.
   Global Scope:
   A variable that's not inside of any function or block (a pair of curly braces) is inside the global scope. The varibales inside a global cope can be accessed from anywhere in the program.
   for eg
   var name = 'Nikhat'
         
         function printName(){
            console.log(name)
         }
         
         printName(); >>>prints Nikaht
   
   Local scope or function scope:
   Variables declared inside a funciton have local scope. They can only be accessed from inside of the function. So they are not available for use outside of the function.
   for eg:
         var name = 'Nikhat'
         
         function printName(){
                  var name = 'Nikhat'
                  console.log(name)
         }
         
         console.log(name) >>> reference error
   
   Block Scope:
   ES6 introduced let and const variables. Unlike var, let and const can be scoped to the nearest pair of curly braces. That means they cant be accessed from outside the pair of curly braces.
   for eg:
                     {
                         let name = 'Nikhat'
                         var surname = 'Shaikh'
                         const country = 'India'
                     }
            
            console.log(name) >>> reference error
            console.log(surname) >>> no error as var has global/function scope, not block scope
            console.log(country) >>> reference error
            
    Notes for me:
         • Anything defined inside of a function (be it var, const or let): not accessbile outside of the function.
         • Anything defined inside of the global scope (be it var, const or let): can be accessed from anywhere in the program
         • let and const inside of a block: cannot be accessed outside of that block. var inside of a block, can be accessed outside of that block
         
   # Scope chain
     Whenever our code tries to access a variable, it starts searching from the varibales inside of the current scope. If in the current scope it doesnt find thee variables, it continues searching for them in the immediately following outer scope and then the next outer scope and so on until it finds the variable or reaches the global scope. THis is called a scope chain.
         

# 7. What's the output:
     const language = 'Brazilian';
     const name = 'Ana';
     
     function displayIntroduction() {
        const name = 'Maria';
        const country = 'Brazil';
        
        function displayInfo() {
          const name = 'Joana';
          console.log(`My name is ${name}, I am from ${country} and I speak ${language});
        }
        
        return displayInfo();
     }
     
     displayIntroduction();
 
 A. it will log : My name is Joana, I am from Brazil and I speak Brazilian.
    The reason is: 
    
# 8. Take an array of six elements, attach splice and alice methods to it and explian them both.
A.   var array = [1, 2, 3, 4, 5, 6];

     array.splice(); 
     overwrites the original array
     given only two arguments say 2 and 1, splice will remove 1 element (2nd argument) starting from the position of 2nd index (1st argument)
     so the first argument is the position from where we want to remove, and the second argumnet is how many elements we want to remove
     for eg:
        array.splice(2, 1) >>> returns array as [1, 2, 4, 5, 6] i.e. 3 is removed
        
     given more than two arguments, splice will add at position i.e. 1st argument, remove number of elments i.e. tne second argument, and will add the given elements from 3rd argumnet onwards
     for eg:
        array.splice(2, 0, 10, 11) >> will add 10 and 11 starting from 2nd index, removing 0 elements i.e array will become [1, 2, 10, 11, 3, 4, 5, 6]
        array.splice(2, 1, 10, 11) >> will add 10 and 11 starting from 2nd inddex, removing 1 element at 2nd index i.e. array will become [1, 2, 10, 11, 4, 5, 6]
        array.splice(2, 2, 10, 11) >> will add 10 and 11 starting from 2nd inddex, removing 2 element from 2nd index i.e. array will become [1, 2, 10, 11, 5, 6]
        
     
     array.slice(startIndex, endIndex); returns a chunk of array from the start index to the endIndex-1. so for eg if we do array.splice(2, 5), this will return the  part of the array from index 2 to index 4 i.e. [3, 4, 5] 
     
# 9. Explain map(), reduce(), filter(), forEach methods in array.
A.   map():
         creates a new array. calls the given function for each element of the array
         var array1 = [1, 2, 3, 4, 5]
         var newArray = array1.map(el => {return el * 2});  // returns a new array with doubled values
         
     reduce():
         takes two arguments and performs the given operation on the two of them returing only a single value at the end, thus called reduce.
         var arr = [100, 40, 10];
         var reducedResult = arr.reduce((el1,el2) => return el1 - el2);
         //returns 40
         
    filter():
         as the name suggests, this method filters throught the gven array and returns all array elements whihc satisfy the given condition
         returns a new array containing all elements that satisfy the given condition
         for eg
         var arr = [1, 2, 4, 5, 10, 11, 15, 20];
         var newArray = arr.filter(el => {return el >= 10});
    
    forEach():
         this mthod is used to iterate over the array
         for eg:
         sum of all array elements
         var arr = [1, 10, 20, 30];
         var sum = 0;
         arr.forEach(el => return sum += el);
         

# 10. Callback functions and its example. What is Callback Hell and how can it be avoided?
A.    Callback Function:
      A callback is a function passed as an argument to another function.
      Where callbacks really shine are in asynchronous functions, where one function has to wait for another function (like waiting for a file to load).
      A typical example is JavaScript setTimeout().
         setTimeout(myFunction, 3000);

         function myFunction() {
           console.log('I am a callback function');
         }
      here, myFuncton is the callback function passed an a argumnt another function, the setTimeout function. 
      And myFunction will be called after 3 seconds
      
      Callback hell and how to avoid it:
      Callback hell refers to the situation where callbacks are nested within other callbacks several levels deep, potentially making it difficult to understand and maintain the code
      There are multiple solutions to avoiding callback hell such as:
      Split the callbacks into different functions
      Use Promises  
      Use Async await

# 11. getters and setters in an object

# 12. Object Destructuring and Array Destructuring
A.    Destructuring in a JS makes it possible to kind of unpack values from arrays or properties from  objetcs 

# 13. Event loop in JS

# 14. What are promises, give an example and explain the stages of promises in JS
A.    

# 15. Spread operator and Rest Operator

# 16. Higher Order Functions in JS

# 17. What is DOM?

# 18. Async await

# 19. Hoisting

# 20. Explain the 'this' keyword with reference to functions

# 21. Difference between arrow functions and regular functions

# 22. What is temporal dead zone?

# 23. Different types of loops in JS

# 24. For of loop implementation

# 25. What are template literals?

# 26. var, let and const difference

# 27. What are timers? Explain setTimeOUt and setInterval

# 28. What are event listeners?

# 29. Different types of events in JS

# 30. What are synchronous and asynchronous functions
      Asynchronous functions:
         use the async keyword before any function declaration (including arrow funtion) to make it asynchronous
         Asynchronous functions always return promises
         It doesnt matter what you return...the returned value will always be a promise.

# 31. What will be the output and why:
      a = 10;
      console.log(a);
      var a;
      What if we change the keywork to be let or const from var
  A.  Output will be 10.
      This is because of a default behaviour of JS called Hoisting.
      While executing any JS code, the complier first runs through the code and brings all the variable and function declarations, not initialistion, ony declariotns, to the top of the scope. So in our example, although var a is declared after we're assigining it a value and loggin it to the console, JS engine will bring the declaration on line 3 to the top of the scope. Now that there is a varibale a declared at the top, then we assign it a value of 10 and then log it to the console, the output willbe 10.
      
      If we had used const or let to decalre the varibale a:
      In case of const, it will clearly be a syntax error because const variables as a rule have to initialised at the time of declaration. 
      In case of let...hoisting works slightly differenlty than the var declations. Let and const variables declarations are stored in memory called the Temporal Dead Zone.
      -remaining
      
# 32. What will be the output and why?
      let a = 3;
      let b = new Number(3);
      let c = 3;
      
      console.log(a == b);
      console.log(a === b);
      console.log(a === c);
A.    a == b: true as the == comparator only compares values nad not data types. here although a and b are of two different data types a is a primitive of type number and b is an object of the Number class..they have the same value. thus, true. 
      a === b: false as the === comparator operator compares the value as well as data type. a and b both have the same value, but their data types are different. while a is a primitive data type of type number, b is an object.
      a === c: true as a and c both are primitites, of type number and have the same value. so when the === comparator compares their value as well as their data type it finds them both to be the same. so it returns true.
      
# 33. Change the html text to 'I am new text' using DOM
      <div id='text'>I am text</div>
      <button id='btn'>Click</button>
      
      
# What is Prototype
     
 

