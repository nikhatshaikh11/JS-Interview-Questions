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
A. var user = {
      id: 1,
      name: 'Nikhat'
   }
   
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
A. 

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


# 10. Callback functions and its example. What is Callback Hell and how can it be avoided?

# 11. getters and setters in an object

# 12. Object Destructuring and Array Destructuring

# 13. Event loop in JS

# 14. What are promises, give an example and explain the stages of promises in JS

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
      
      

     
 

