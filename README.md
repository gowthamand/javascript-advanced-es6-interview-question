# JavaScript ES6 Interview Questions & Answers

### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is IIFE's (Immediately-Invoked Function Expression)](#what-is-iifes)|
|2 | [What's the difference between .call and .apply?](#whats-the-difference-between-call-and-apply)|
|2 | [What's the difference between using “let” and “var” to declare a variable in ES6?](#whats-the-difference-between-using-let-and-var-to-declare-a-variable-in-es6)|
 

1. ### What is IIFE's

    It’s an Immediately-Invoked Function Expression, or IIFE for short. It executes immediately after it’s created.
    It has nothing to do with any event-handler for any events (such as document.onload).
Consider the part within the first pair of parentheses: ```(function(){})();```....it is a regular function expression. Then look at the last pair ``` (function(){})(); ```, this is normally added to an expression to call a function; in this case, our prior expression.
   
   This pattern is often used when trying to avoid polluting the global namespace, because all the variables used inside the IIFE (like in any other normal function) are not visible outside its scope.
This is why, maybe, you confused this construction with an event-handler for window.onload, because it’s often used as this
  ```typescript
    (function(){
      var foo = function() {};
      window.onload = foo;
    })(); 
  
    (function IIFE(){
      console.log( "Hello!" );
    })();
  ```
**[⬆ Back to Top](#table-of-contents)**  

2. ### What's the difference between .call and .apply?
    Both .call and .apply are used to invoke functions and the first parameter will be used as the value of this within the function. However, .call takes in comma-separated arguments as the next arguments while .apply takes in an array of arguments as the next argument. An easy way to remember this is C for call and comma-separated and A for apply and an array of arguments.
  ```typescript
     function add(a, b){
        return a + b;
     }
     console.log(add.call(null, 1, 2)); // 3
    console.log(add.apply(null, [1, 2])); // 3
  ```
**[⬆ Back to Top](#table-of-contents)**

3. ### What's the difference between using “let” and “var” to declare a variable in ES6?
  Main difference is scoping rules. Variables declared by ``var`` keyword are scoped to the immediate function body (hence the function scope) while ``let`` variables are scoped to the immediate enclosing block denoted by `` { } `` (hence the block scope).
  ```typescript
  function run() {
   var foo = "Foo";
   let bar = "Bar";

   console.log(foo, bar);

   {
     let baz = "Bazz";
     console.log(baz);
   }

   console.log(baz); // ReferenceError
  }

run();
  ```
  **[⬆ Back to Top](#table-of-contents)**
