# js-in-deep

JavaScript is a synchronous, single thread language

- Synchronous: A line per line in order
- Single Thread:  1 line per time


Execute  context Context of JS:

Memory: Variable Environment
Code: Thread Execution


JS runs a program  in 2 phases:

- Memory Creation Phase: Create all variables (allocate memory) with undefined and functions with the code.
- Code Execution Phase: Execute the code: make operations

Functions create a new Execution Context and after run the function context is deleted

Global Execution is deleted after all


The Global execution Context and execution contexts are inside the call stack


----------------------------------------------------------

JS hoisting:

As on the first run the JS declare every variable as undefined and the function as the code.

So if I try access a variable before be declared on the code the answer will be undefined

In the case of the function will work


--------------------------------------------------------

Lexical enviroment:

Local memory along with the lexical environment with the parent

- Hierarque


function a () {
	function c() {
	}
}

c is lexical inside a, a is lexical inside the Global scope


Lexical environment of c: c + reference of the Memory a
Lexical environment of a: a + reference of the Memory Global Execution Context
Lexical environment of Global Execution Context: Global Execution Context + null

Scope chain -> references between a execute context and your parents 

How is the cost of try to access the Lexical environment of the father?

-------------------------------------------------------------------
Let and const are different than var

var and functions are hoisted in the memory creation phase
let and const are allocated in the memory, but not on the Global Scope, the temporary dead zone - between the memory create phase and the assign the variable

When you open a console, before and after the code run var is accessible, but let and const no 
let and const don't allow redeclaration

-----------------------------------------------------
TypeError: Error of type -> let, var, const -> try to assign a const
SyntaxError: const with assigning, let redeclaration
ReferenceError: couldn't find the variable on the memory 

------------------------------------------------------------

Block Scope / Compound Statment 

JS waits for 1 statement, so to use multiple statements is need to be grouped in a Compound Statement

let and const are accessible only inside the Block Scope


Shadowing

let a = 10;
{
  let a = 1;
}

Declarations with the same name will get more inner scope value;

The behavior is different between var and let/const

Global, Block, and Script Scopes of the same Execute Context

Ilegal Shadowing

- Try to shadow a let using a var

Shadowing may not cross the limit of the scope, but var does this, therefore if the shadowing is var -> var  both will point to the same place - change inside a scope will change inside a scope
In the case of let -> var, JS understands var as a redeclaration of the let

Nested scopes create new Scopes, but not new Context
var is declared on the Context so can be accessible in any Scope ignoring the lexical other. 

1. Code inside curly bracket is called block.
2. Multiple statements are grouped inside a block so it can be written where JS expects single statements like in if, else, loop, function etc.
3. Block values are stored inside separate memory than global. They are stored in block. (the reason let and const are called block scope)
4. Shadowing of variables using var, let and const.
5. The shadow should not cross the scope of original otherwise it will give error.
6. shadowing let with var is illegal shadowing and gives error.
7. var value is stored in nearest outer function or global scope and hence can be accessed outside block as well whereas same is not the case with let and const.




