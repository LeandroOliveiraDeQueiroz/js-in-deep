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



JS wait for 1 statement, so to use multiple statements is need to be group in a Compound Statment



