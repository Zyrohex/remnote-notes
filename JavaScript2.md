- ## JavaScript Programming
	- Overview
		- A high-level, interpreted programming language primarily used to add interactivity to web pages.
	- Basic Components of JavaScript
		- [[Variables]]
		  collapsed:: true
			- What are Variables?
				- A variable is a named storage for data. To declare a variable in JavaScript, we could use 'var', 'let', or 'const' keywords.
			- What keywords are there to work with variables?
				- var
				  collapsed:: true
					- 'var' is the oldest keyword to declare a variable in JavaScript.
					- A variable declared with 'var' is function-scoped, meaning its scope is limited to the function in which it is declared. If it is declared outside any function, it is globally scoped.
					- 'var' variables can be redeclared and updated.
				- let
				  collapsed:: true
					- 'let' is a newer keyword introduced in ES6 (ECMAScript 2015) for declaring variables.
					- A variable declared with 'let' is block-scoped, meaning its scope is limited to the block (defined by curly braces {}) in which it is declared.
					- 'let' variables can be updated but not redeclared.
				- const
				  collapsed:: true
					- 'const' is another keyword introduced in ES6 for declaring variables.
					- A variable declared with 'const' is block-scoped like 'let'.
					- 'const' variables cannot be updated or redeclared. They are constant, meaning their value cannot be changed after they are initially set.
					- Note that for 'const' objects, the object itself cannot be reassigned, but its properties can be updated.
			- Hoisting
				- In JavaScript, variable declarations (not initializations) are "hoisted" to the top of their scope. This means that a variable can be used before it's declared.
				- 'var' variables are initialized with 'undefined', while 'let' and 'const' variables are not initialized.
			- Naming
				- Variable names in JavaScript can contain letters, digits, underscores (_), and dollar signs ($).
				- Variable names cannot start with a digit.
				- JavaScript variable names are case-sensitive. For instance, `myVar` and `myvar` are different variables.
				- There are reserved words in JavaScript that cannot be used as variable names, such as `let`, `var`, `const`, `function`, and many others.
			- Data Types
				- Variables in JavaScript are dynamically typed. This means a variable can be of one data type and later be reassigned a value of a different data type.
				- JavaScript provides several types of data that can be stored in variables: `Number`, `String`, `Boolean`, `Object`, `Null`, `Undefined`, `Symbol`, and `BigInt`.
				- For complex data, JavaScript provides `Object` data type that can be used to store collections of data.
			- Variable Scope
				- Global Variables: If a variable is declared outside all functions or curly braces (`{}`), it is a global variable and can be accessed from any part of the code.
				- Local Variables: If a variable is declared inside a function or a block, it is a local variable and can be accessed only within that function or block.
			- Variable Assignments
				- Variables in JavaScript can be assigned values using the `=` operator. The value on the right of the `=` operator is assigned to the variable on the left.
				- Variables can be assigned a value at the time of declaration, or can be declared first and assigned a value later in the code.
			- Null and Undefined
				- A variable that has no value assigned to it is `undefined`.
				- A variable can be emptied by setting it to `null`.
			- Conclusion
				- Understanding variables and their behavior is fundamental in JavaScript programming. They are the basic building blocks where we store, manipulate, and work with data.
		- [[Data Types]]
		  collapsed:: true
			- Overview
				- JavaScript has several data types. They include `Number`, `String`, `Boolean`, `Object`, `Null`, `Undefined`, `Symbol`, and `BigInt`.
			- Number
				- Used to represent numerical values.
				- Can be integers, floats, positives, negatives, etc.
				- Special numeric values include `Infinity`, `-Infinity`, and `NaN` (Not a Number).
			- String
				- Used to represent textual data.
				- Enclosed within quotes, which can be single (`'...'`), double (`"..."`), or backticks (`...`).
				- Backticks are used for template literals where you can embed variables and expressions.
			- Boolean
				- Represents a logical entity.
				- Can have only two values, `true` or `false`.
			- [[Objects]]
				- Overview
					- Objects in JavaScript are entities with properties. The properties are basically keys, each of which has a value.
					- They are used to store collections of data or more complex entities.
				- Declaring Objects
				  collapsed:: true
					- Objects can be created using curly braces `{...}` with a list of properties. They are also declared with curly braces `{}`. Inside these braces, properties and their values are defined as pairs.
					- Objects in JavaScript are key-value pairs, properties are separated by commas, the property keys can be strings or identifiers, while values can be of any type.
					- For example:
					  ```javascript
					  let car = {
					    make: 'Toyota',
					    model: 'Camry',
					    year: 2020
					  };
					  ```
					- Empty Object
						- An object with no properties is declared as `let objectName = {};`.
					- Object with Properties
						- An object with properties is declared by specifying the property name, followed by a colon `:`, followed by the value of the property.
						- For example: `let car = {make: 'Toyota', model: 'Camry', year: 2020};`
					- Property Values
						- Property values can be of any JavaScript data type, including `Number`, `String`, `Boolean`, `Object`, `Null`, `Undefined`, `Symbol`, `BigInt`, and `Function`.
					- Nested Objects
						- An object can contain other objects as property values. This is often referred to as nested objects.
						- For example: 
						  ```javascript
						  let person = {
						     name: 'John Doe',
						     address: {
						         street: '123 Main St',
						         city: 'Anytown',
						         country: 'USA'
						     }
						  };
						  ```
					- Arrays in Objects
						- Objects can also contain arrays as property values.
						- For example: 
						  ```javascript
						  let person = {
						     name: 'John Doe',
						     hobbies: ['reading', 'gaming', 'coding']
						  };
						  ```
				- [Accessing Object Properties]([[Properties]])
				  collapsed:: true
					- Properties of an object can be accessed using dot notation or bracket notation.
					- Dot notation: `object.property`
					- Bracket notation: `object['property']`
				- [Object Methods]([[Methods]])
				  collapsed:: true
					- Methods are actions that can be performed on objects. They are stored as function properties.
					- For example:
					  ```javascript
					  let car = {
					    start: function() {
					      console.log('Car started.');
					    }
					  };
					  ```
					- Methods can be accessed like properties: `car.start();`
				- [[This]]
				  collapsed:: true
					- When a function is called as a method of an object, `this` is set to the object the method is called on.
					- Example:
					  ```javascript
					  let car = {
					     make: 'Toyota', 
					     model: 'Camry', 
					     start: function() { 
					         console.log(this.make + ' ' + this.model + ' started.'); 
					     }
					  };
					  car.start();  // "Toyota Camry started."
					  ```
					- Here, `this` inside the `start` function is referring to the `car` object.
				- [Object Constructors]([[Constructors]])
				  collapsed:: true
					- Overview
						- Constructors are special functions used to create objects of the same type.
						- They are the blueprints from which individual objects are created.
					- Declaring Constructors
						- Constructors are declared like regular functions, but the convention is to start with a capital letter.
						- A constructor function can use the `this` keyword to assign values to the new object's properties based on the arguments passed.
						- For example: 
						  ```javascript
						  function Car(make, model, year) {
						     this.make = make;
						     this.model = model;
						     this.year = year;
						  }
						  ```
					- Creating Objects from Constructors
						- To create a new object from a constructor function, you use the `new` keyword.
						- For example: `let car1 = new Car('Toyota', 'Camry', 2020);`
						- This creates a new instance of the `Car` object, with the properties defined within the `Car` constructor function.
					- Constructors with Methods
						- Constructors can also define methods.
						- For example:
						  ```javascript
						  function Car(make, model, year) {
						     this.make = make;
						     this.model = model;
						     this.year = year;
						     this.displayCar = function() {
						         return this.make + ' ' + this.model;
						     }
						  }
						  ```
						- Now, all objects created with this constructor will have a `displayCar` method: `let car1 = new Car('Toyota', 'Camry', 2020); car1.displayCar(); // "Toyota Camry"`
					- Conclusion
						- Object constructors provide a way to create multiple similar objects with the same property names and methods. This becomes extremely useful in cases where you want to instantiate multiple instances of an object, like users in a database, products in a shopping cart, or similar scenarios.
				- [[Prototypes]]
					- JavaScript objects inherit properties and methods from a prototype.
					- The `Object.prototype` is on the top of the prototype chain.
					- All JavaScript objects can use the methods and properties from the `Object.prototype`.
				- Conclusion
					- The Object data type is one of the fundamental building blocks in JavaScript. It allows for the storage of complex structures and provides the foundation for object-oriented programming.
			- Null
				- Represents the intentional absence of any object value.
				- It is often used to denote or clear a variable.
			- Undefined
				- A variable that has been declared, but not assigned a value, is `undefined`.
			- Symbol
				- Overview
					- Introduced in ECMAScript 2015 (ES6), a `Symbol` is a unique and immutable data type that is often used to identify object properties.
					- To create a `Symbol`, you write `Symbol()` with an optional string as its description.
				- Creating Symbols
					- Overview
						- The `Symbol()` function is used to create a new Symbol.
						- Every time you call the `Symbol()` function, a new and unique Symbol is created.
					- Creating Symbols
						- You can create a Symbol by calling the `Symbol()` function, with an optional string as its description: `let symbol1 = Symbol('description')`.
						- The description is just a label that helps during debugging – it's not used for accessing the Symbol itself.
					- Uniqueness of Symbols
						- Each Symbol is unique. Even if you create many Symbols with the same description, they are different.
						- Example:
						  ```javascript
						  let symbol1 = Symbol('description');
						  let symbol2 = Symbol('description');
						  console.log(symbol1 === symbol2);  // false
						  ```
						- Here, `symbol1` and `symbol2` are different Symbols, even though their descriptions are the same.
					- Symbols and Coercion
						- Symbols are not implicitly converted to a string or a number, in contrast to other JavaScript types.
						- For instance, this will throw an error:
						  ```javascript
						  let symbol1 = Symbol('description');
						  let str = 'my string ' + symbol1; // TypeError
						  ```
						- But, Symbols can be explicitly converted to a string:
						  ```javascript
						  let symbol1 = Symbol('description');
						  let str = 'my symbol ' + symbol1.toString(); // "my symbol Symbol(description)"
						  ```
					- Conclusion
						- Symbols are a unique and powerful feature in JavaScript, providing a way to create non-colliding property keys on objects, among other uses. Understanding how to create and work with Symbols is a key part of mastering the language.
				- Uniqueness of Symbols
					- Every time you call the `Symbol()` function, a new and unique `Symbol` is created, even if you already have a symbol with the same description: `Symbol('description') !== Symbol('description') // true`.
					- Example:
					  ```javascript
					  let symbol1 = Symbol('description');
					  let symbol2 = Symbol('description');
					  console.log(symbol1 === symbol2);  // false
					  ```
					- Here, `symbol1` and `symbol2` are different Symbols, even though their descriptions are the same.
				- Symbol as Object Properties
					- Symbols can be used as object property identifiers.
					- When a `Symbol` is used as a property key, that property is public (can be accessed outside the object), but it's not enumerable (won't show up in a `for...in` loop or `Object.keys()`).
					- Example:
					  ```javascript
					  let symbol1 = Symbol('description');
					  let obj = {
					     [symbol1]: 'value'
					  };
					  console.log(obj[symbol1]);  // "value"
					  ```
				- Global Symbol Registry
					- The Global Symbol Registry is a mechanism in JavaScript where Symbols are stored and can be retrieved for reuse. This is useful for referencing the same Symbol across different parts of your application.
					- `Symbol.for(key)`
						- The `Symbol.for(key)` method is used to create or fetch a Symbol from the global symbol registry.
						- If a Symbol with the provided key exists in the registry, `Symbol.for(key)` will retrieve it. If not, it creates a new Symbol with the given key and adds it to the registry.
						- Example:
						  ```javascript
						  let symbol1 = Symbol.for('description');
						  let symbol2 = Symbol.for('description');
						  console.log(symbol1 === symbol2);  // true
						  ```
						- In this case, `symbol1` and `symbol2` are the same Symbol because they were both retrieved from the global symbol registry with the same key.
					- `Symbol.keyFor(symbol)`
						- The `Symbol.keyFor(symbol)` method is used to retrieve the key for a Symbol in the global symbol registry.
						- This only works for Symbols present in the global symbol registry.
						- Example:
						  ```javascript
						  let symbol1 = Symbol.for('description');
						  console.log(Symbol.keyFor(symbol1));  // "description"
						  ```
					- Conclusion
						- The Global Symbol Registry provides a way to access and share Symbols across your entire JavaScript runtime. It ensures that you can use the same Symbol in different parts of your application, enabling more complex interactions and patterns.
				- Conclusion
					- The `Symbol` data type, with its unique and immutable characteristics, provides a robust way to attach properties to objects without risking property name collisions. It's especially useful in complex applications and shared libraries.
			- BigInt
				- Introduced in ES10 (ECMAScript 2020).
				- It is used to store very large integer numbers, beyond the safe limit for `Number` type.
			- Type Coercion
				- JavaScript is a loosely typed or a dynamic language. Variables in JavaScript are not directly associated with any particular value type, and any variable can be assigned (and re-assigned) values of all types.
				- Type coercion means that when the operands of an operator are different types, one of them will be converted to an "equivalent" value of the other operand's type.
				- JavaScript performs type coercion in certain situations, automatically converting a value from one type to another.
				- Coercion can be implicit (done by JavaScript engine) or explicit (done by the programmer).
			- Checking Types
				- JavaScript provides the `typeof` operator to check the type of a variable.
				- It returns a string indicating the type of the unevaluated operand.
				- It can return the following values: `"Number"`, `"String"`, `"Boolean"`, `"Undefined"`, `"Object"`, `"Function"`, `"Symbol"`, and `"BigInt"`.
				- However, it has limitations. For instance, `typeof null` returns `"object"`, and `typeof` an array also returns `"object"`.
			- Truthy and Falsy Values
				- Every value in JavaScript has an inherent boolean truthy or falsy value.
				- Falsy values are values that, when converted to a boolean, become `false`. In JavaScript, they are `false`, `0`, `""` (empty string), `null`, `undefined`, and `NaN`.
				- Everything else is considered truthy.
			- Comparison and Equality
				- JavaScript has both strict comparison (`===`) and loose comparison (`==`).
				- Loose comparison (`==`) checks for equality of value, but not equality of type. This comparison performs type coercion.
				- Strict comparison (`===`) checks for equality of value and type. This comparison does not perform type coercion.
			- Conclusion
				- Understanding each of these data types and when to use them is crucial in JavaScript programming, as it helps in storing and manipulating data efficiently.
		- [[Operators]]
		  collapsed:: true
			- Overview
				- Operators are symbols that tell the JavaScript engine to perform specific mathematical or logical manipulations.
			- Types of Operators
				- **Arithmetic Operators**: Used to perform arithmetic between variables and/or values.
					- Example: `+`, `-`, `*`, `/`, `%`, `++`, `--`.
				- **Assignment Operators**: Used to assign values to JavaScript variables.
				  collapsed:: true
					- Overview
						- Assignment operators are used to assign values to variables.
					- Basic Assignment Operator
						- `=`: Assigns the value on the right to the variable on the left.
						- Example: `let x = 5;`
					- Compound Assignment Operators
						- Compound assignment operators are shorthand operators that modify the value of the variable using the operator and the right operand and then assign the result to the variable.
						- `+=`: Addition assignment. It adds the right operand to the left operand and then assigns the result to the left operand.
							- Example: `x += 3; // same as x = x + 3;`
						- `-=`: Subtraction assignment. It subtracts the right operand from the left operand and then assigns the result to the left operand.
							- Example: `x -= 3; // same as x = x - 3;`
						- `*=`: Multiplication assignment. It multiplies the left operand by the right operand and then assigns the result to the left operand.
							- Example: `x *= 3; // same as x = x * 3;`
						- `/=`: Division assignment. It divides the left operand by the right operand and then assigns the result to the left operand.
							- Example: `x /= 3; // same as x = x / 3;`
						- `%=`: Remainder assignment. It divides the left operand by the right operand, calculates the remainder, and then assigns the result to the left operand.
							- Example: `x %= 3; // same as x = x % 3;`
						- There are also compound assignment operators for bitwise and logical operations.
					- Conclusion
						- Assignment operators in JavaScript make it easy to perform an operation on a variable and then assign the result to that same variable.
				- **Comparison Operators**: Used in logical statements to determine equality or difference between variables or values.
				  collapsed:: true
					- Overview
						- Comparison operators are used to compare two values and return a boolean result (true or false) depending on whether the comparison is true.
					- Equality Operators
						- `==`: Equality operator. It compares two values for equality after converting both to a common type, if necessary. This is known as type coercion.
							- Example: `5 == "5";  // true`
						- `===`: Strict equality operator. It compares two values for equality, without converting type. Both value and type must be the same for it to return true.
							- Example: `5 === "5";  // false`
						- `!=`: Inequality operator. It compares two values for inequality, performing type coercion if necessary.
							- Example: `5 != "5";  // false`
						- `!==`: Strict inequality operator. It compares two values for inequality, without converting type.
							- Example: `5 !== "5";  // true`
					- Relational Operators
						- `<`: Less than operator. It checks whether the left value is less than the right value.
							- Example: `5 < 10;  // true`
						- `>`: Greater than operator. It checks whether the left value is greater than the right value.
							- Example: `5 > 10;  // false`
						- `<=`: Less than or equal to operator. It checks whether the left value is less than or equal to the right value.
							- Example: `5 <= 5;  // true`
						- `>=`: Greater than or equal to operator. It checks whether the left value is greater than or equal to the right value.
							- Example: `5 >= 10;  // false`
					- Conclusion
						- Comparison operators in JavaScript are fundamental to controlling the flow of code, particularly in if statements and loops.
						- It's important to understand the difference between `==` and `===`, as well as `!=` and `!==`, as they can yield different results due to type coercion.
				- **Logical Operators**: Used to determine the logic between variables or values.
				  collapsed:: true
					- Example: `&&`, `||`, `!`.
				- **Bitwise Operators**: Used to work on 32-bit binary numbers.
				  collapsed:: true
					- Overview
						- Bitwise operators perform operations on binary representations of numbers. Each operand is treated as a set of bits rather than as a single number.
					- Bitwise AND (`&`)
						- The `&` operator compares each bit of the first operand to the corresponding bit of the second operand. If both bits are 1, the corresponding result bit is set to 1. Otherwise, the corresponding result bit is set to 0.
						- Example: `5 & 3;  // 1 (because binary 101 & 011 = 001)`
					- Bitwise OR (`|`)
						- The `|` operator compares each bit of the first operand to the corresponding bit of the second operand. If either bit is 1, the corresponding result bit is set to 1. Otherwise, the corresponding result bit is set to 0.
						- Example: `5 | 3;  // 7 (because binary 101 | 011 = 111)`
					- Bitwise XOR (`^`)
						- The `^` operator compares each bit of the first operand to the corresponding bit of the second operand. If exactly one of the bits is 1, the corresponding result bit is set to 1. Otherwise, the corresponding result bit is set to 0.
						- Example: `5 ^ 3;  // 6 (because binary 101 ^ 011 = 110)`
					- Bitwise NOT (`~`)
						- The `~` operator inverts the bits of its operand.
						- Example: `~5;  // -6 (because binary ~101 = 010, which represents -6 in two's complement)`
					- Left Shift (`<<`)
						- The `<<` operator shifts the bits of the first operand to the left by the number of places specified by the second operand. New bits on the right are filled with zeros.
						- Example: `5 << 1;  // 10 (because binary 101 << 1 = 1010)`
					- Right Shift (`>>`)
						- The `>>` operator shifts the bits of the first operand to the right by the number of places specified by the second operand. The sign of the number is preserved.
						- Example: `5 >> 1;  // 2 (because binary 101 >> 1 = 10)`
					- Zero-Fill Right Shift (`>>>`)
						- The `>>>` operator shifts the bits of the first operand to the right by the number of places specified by the second operand. New bits on the left are filled with zeros. This operator does not preserve the sign of the number.
						- Example: `-5 >>> 1;  // 2147483645 (because binary -101 >>> 1 = 1111111111111111111111111111110)`
					- Conclusion
						- Bitwise operators are less commonly used than other JavaScript operators, but they are useful in certain situations, particularly when dealing with binary data.
				- **Ternary Operator (Conditional)**: Used as a shortcut for the if statement.
				  collapsed:: true
					- Overview
						- The ternary operator is a shorthand way of writing simple `if...else` statements. It's called the ternary operator because it takes three operands - a condition, a statement to execute when the condition is true, and a statement to execute when the condition is false.
					- Syntax
						- The syntax of the ternary operator is: `condition ? expressionIfTrue : expressionIfFalse;`
					- Using the Ternary Operator
						- The way you use the ternary operator is first to provide a condition, followed by a question mark, then an expression to execute if the condition is true, followed by a colon (:), and finally an expression to execute if the condition is false.
						- Example:
						  ```javascript
						  let age = 15;
						  let type = age >= 18 ? 'Adult' : 'Minor';
						  console.log(type);  // "Minor"
						  ```
						- In this example, the condition `age >= 18` is false, so the expression after the colon (`'Minor'`) is assigned to the variable `type`.
					- Chaining Ternary Operators
						- You can chain ternary operators to check for multiple conditions.
						- Example:
						  ```javascript
						  let age = 65;
						  let type = age < 18 ? 'Minor' : age >= 65 ? 'Senior' : 'Adult';
						  console.log(type);  // "Senior"
						  ```
						- This works like an `if...else if...else` statement. In the example above, since `age < 18` is false, it moves on to the next condition `age >= 65`. Because this is true, `'Senior'` is assigned to `type`.
					- Conclusion
						- The ternary operator provides a concise way to write simple conditional statements. However, they can become difficult to read when nested or chained, so use them sparingly and wisely.
				- **String Operators**: JavaScript uses the `+` operator to concatenate strings, or add strings together.
				  collapsed:: true
					- Example:
					  ```javascript
					  let text1 = "Hello";
					  let text2 = "World";
					  console.log(text1 + " " + text2);  // "Hello World"
					  ```
				- **Type Operators**: JavaScript has two operators that are used specifically to examine the type of a variable.
				  collapsed:: true
					- `typeof`: Returns a string that indicates the type of the unevaluated operand.
						- Example: `console.log(typeof 'Hello');  // "string"`
					- `instanceof`: Tests whether an object is an instance of a specific class or an object has a prototype in its prototype chain.
						- Example: `console.log('Hello' instanceof String);  // false`
				- **Void Operator**: The `void` operator discards the return value of an expression.
				  collapsed:: true
					- Overview
						- The `void` operator evaluates the given expression and then returns `undefined`. This is useful in situations where you want to explicitly get the `undefined` value or prevent a value from being returned.
					- Basic Usage
						- `void expression`: Evaluates the `expression`, then returns `undefined`.
						- Example: `void 0;  // returns undefined`
						- Example: `void(0);  // also returns undefined`
					- Common Use Cases
						- Using `void 0` or `void(0)` is a reliable way to obtain the `undefined` value because, unlike the `undefined` property of the global object, the `void` operator cannot be overridden.
						- The `void` operator is often used in JavaScript URIs (e.g., `javascript:void(0);`) to prevent the browser from refreshing the page. Normally, the browser replaces the current page with the result of evaluating the JavaScript URI. If this result is `undefined`, as it is when the `void` operator is used, the browser stays on the current page.
					- Conclusion
						- While the `void` operator is less commonly used in modern JavaScript development, it can be handy in certain scenarios. Its main purpose is to ensure that a JavaScript expression evaluates to `undefined`.
				- **Delete Operator**: Removes a property from an object.
				  collapsed:: true
					- Example:
					  ```javascript
					  let obj = {name: 'John', age: 30};
					  delete obj.age;
					  console.log(obj);  // {name: 'John'}
					  ```
				- **In Operator**: Returns `true` if the specified property is in the specified object or its prototype chain.
				  collapsed:: true
					- Example:
					  ```javascript
					  let obj = {name: 'John', age: 30};
					  console.log('name' in obj);  // true
					  ```
				- **Comma Operator (,)**: Evaluates each of its operands and returns the value of the last one.
				  collapsed:: true
					- Example:
					  ```javascript
					  let a = (3, 5);
					  console.log(a);  // 5
					  ```
				- **Spread Operator (...)**
				  collapsed:: true
					- Overview
						- The spread operator (`...`) is used to expand iterable elements into individual elements. It can be used in array literals, object literals, function calls, and in the destructuring assignment syntax.
					- [Usage in Arrays]([[Arrays]])
						- In array literals: It expands an array into its elements.
							- Example: `let arr1 = [1, 2, 3]; let arr2 = [...arr1, 4, 5];  // arr2 is now [1, 2, 3, 4, 5]`
						- In function calls: It expands an array into separate arguments.
							- Example: `let arr = [1, 2, 3]; Math.max(...arr);  // returns 3`
						- In destructuring assignments: It allows remaining elements of an array to be assigned to a new array.
							- Example: `let arr = [1, 2, 3, 4, 5]; let [a, ...rest] = arr;  // a is 1, rest is [2, 3, 4, 5]`
					- [Usage in Objects]([[Objects]])
						- In object literals: It copies properties from one object into a new object. This is useful for creating a copy of an object with modifications.
						- Example:
						  ```javascript
						  let obj1 = {
						    a: 1,
						    b: 2
						  }; 
						  let obj2 = {
						    ...obj1,
						    c: 3
						  };
						  // obj2 is {a: 1, b: 2, c: 3}
						  ```
					- Conclusion
						- The spread operator is a powerful feature in JavaScript that allows for efficient manipulation of arrays and objects, making your code cleaner and more readable.
			- Using Operators
				- Operators are used in JavaScript to manipulate data and variables.
				- Examples:
				  ```javascript
				  let a = 5;
				  let b = 2;
				  console.log(a + b);  // 7 (Arithmetic)
				  a += b;  // a = a + b (Assignment)
				  console.log(a === b);  // false (Comparison)
				  console.log(a > b && b < a);  // true (Logical)
				  console.log(a > b ? a : b);  // 7 (Ternary)
				  ```
			- Conclusion
				- Operators are the building blocks of any programming language and understanding how to use them effectively is key to writing clean, efficient JavaScript code.
		- [[Control Structures]]
		  collapsed:: true
			- Control structures allow you to manipulate the flow of code execution based on certain conditions or loops. They are essential to making your code dynamic and responsive to different situations.
			- [[Conditional Statements]]
			  collapsed:: true
				- `if`: Executes a block of code if a specified condition is true.
					- Example: `if (condition) { // code to be executed if the condition is true }`
				- `else`: Executes a block of code if the condition in the `if` statement is false.
					- Example: `if (condition) { // code to be executed if the condition is true } else { // code to be executed if the condition is false }`
				- `else if`: Specifies a new condition if the first condition is false.
					- Example: `if (condition1) { // code to be executed if condition1 is true } else if (condition2) { // code to be executed if condition2 is true } else { // code to be executed if the conditions are false }`
				- `switch`: Selects one of many code blocks to be executed, based on the value of a variable or expression.
					- Example: 
					  ```javascript
					  switch(expression) {
					    case value1:
					        // code to be executed if expression equals value1
					        break;
					    case value2:
					        // code to be executed if expression equals value2
					        break;
					    default:
					        // code to be executed if expression doesn't match any cases
					  }
					  ```
			- [[Looping Statements]]
			  collapsed:: true
				- Looping statements are used to repeatedly execute a block of code as long as a certain condition is met. They're crucial for performing repetitive tasks and iterating over data structures.
				- `for` loop
					- The `for` loop is composed of three parts: initialization, condition, and final-expression (generally for incrementing or decrementing).
					- Example: 
					  ```javascript
					  for (let i = 0; i < 5; i++) {
					    console.log(i); // prints numbers 0 to 4
					  }
					  ```
				- `while` loop
					- The `while` loop continues as long as the specified condition evaluates to `true`.
					- Example: 
					  ```javascript
					  let i = 0;
					  while (i < 5) {
					    console.log(i); // prints numbers 0 to 4
					    i++;
					  }
					  ```
				- `do...while` loop
					- Similar to `while`, but the code block is executed at least once before the condition is checked.
					- Example: 
					  ```javascript
					  let i = 0;
					  do {
					    console.log(i); // prints numbers 0 to 4
					    i++;
					  } while (i < 5);
					  ```
				- `for...in` loop
					- The `for...in` loop iterates over the enumerable properties of an object, in an arbitrary order.
					- Example: 
					  ```javascript
					  const obj = {a: 1, b: 2, c: 3};
					  for (let prop in obj) {
					    console.log(`${prop}: ${obj[prop]}`); // prints "a: 1", "b: 2", "c: 3"
					  }
					  ```
				- `for...of` loop
					- The `for...of` loop iterates over iterable objects (including Array, Map, Set, arguments object and so on).
					- Example: 
					  ```javascript
					  const arr = [1, 2, 3, 4, 5];
					  for (let value of arr) {
					    console.log(value); // prints numbers 1 to 5
					  }
					  ```
				- Conclusion
					- Looping statements in JavaScript provide a variety of ways to control the repeated execution of code. The choice of loop often depends on the specific needs and constraints of your situation.
			- [[Error Handling]]
			  collapsed:: true
				- `try...catch...finally`
					- The `try...catch` statements mark a block of code to try and specify a response if an error is thrown. The `finally` statement lets you execute code, after `try` and `catch`, irrespective of the result.
					- Example: 
					  ```javascript
					  try {
					    // Code to try which may throw an error
					  } catch (error) {
					    // Code to run if an error occurs
					  } finally {
					    // Code to be executed regardless of an error
					  }
					  ```
				- `throw`
					- The `throw` statement allows you to create custom errors. Technically, you can throw an exception (throw an error). The exception can be a JavaScript String, a Number, a Boolean or an Object.
					- Example: `throw new Error('This is a custom error');`
			- [[Flow Control]]
			  collapsed:: true
				- `break`
					- The `break` statement, which was briefly mentioned in the switch case, can be used to jump out of a loop and continues executing the code that follows the loop (if any).
					- Example:
					  ```javascript
					  for (let i = 0; i < 10; i++) {
					    if (i === 5) {
					        break; // jump out of the loop
					    }
					    console.log(i);
					  }
					  ```
				- `continue`
					- The `continue` statement can be used to skip one iteration of the loop and continue with the next iteration.
					- Example:
					  ```javascript
					  for (let i = 0; i < 10; i++) {
					    if (i === 5) {
					        continue; // skip this iteration
					    }
					    console.log(i);
					  }
					  ```
			- Conclusion
				- Control structures in JavaScript are fundamental to creating dynamic, responsive code. They enable decision-making, iteration, and the ability to selectively execute code blocks based on certain conditions.
		- [[Functions]]
		  collapsed:: true
			- Functions are reusable blocks of code that perform a specific task. Functions are defined once and can be called (used) multiple times. They can optionally take arguments and return a value.
			- Function Declaration
			  collapsed:: true
				- A function declaration defines a named function.
				- Example:
				  ```javascript
				  function greet(name) {
				    return `Hello, ${name}!`;
				  }
				  ```
			- Function Invocation (Calling)
			  collapsed:: true
				- Functions execute when they are called. This process is known as invocation. You can invoke a function by using parentheses `()` after its name.
				- Example: `greet('John');`
			- Parameters and Arguments
			  collapsed:: true
				- Parameters are names listed in the function definition. Arguments are the real values received by the function when it is invoked.
				- In the example `greet(name)`, `name` is a parameter. When we call `greet('John')`, `'John'` is the argument.
			- Function Scope
			  collapsed:: true
				- Variables defined inside a function cannot be accessed from outside the function. This is due to function scope.
				- Variables defined in the global scope can be accessed by all functions.
			- Default Parameters
			  collapsed:: true
				- In JavaScript, function parameters default to `undefined`. However, you can set your own default values for parameters. These will be used if the function is called without an argument for that parameter, or if the argument is `undefined`.
				- Example:
				  ```javascript
				  function greet(name = 'World') {
				    return `Hello, ${name}!`;
				  }
				  
				  console.log(greet()); // logs 'Hello, World!'
				  console.log(greet('John')); // logs 'Hello, John!'
				  ```
			- Rest Parameters
			  collapsed:: true
				- The rest parameter syntax allows you to represent an indefinite number of arguments as an array.
				- Example:
				  ```javascript
				  function sum(...numbers) {
				    return numbers.reduce((a, b) => a + b, 0);
				  }
				  
				  console.log(sum(1, 2, 3, 4)); // logs '10'
				  ```
			- Function Expression
			  collapsed:: true
				- A function expression defines a function as a part of a larger expression syntax (typically variable assignment). Functions defined via expressions can be anonymous or named.
				- Example:
				  ```javascript
				  const greet = function(name) {
				    return `Hello, ${name}!`;
				  }
				  ```
			- Arrow Functions
			  collapsed:: true
				- Overview
					- Arrow functions are a more concise syntax for writing function expressions. They utilize a new token, `=>`, which looks like an arrow.
				- Syntax
					- The syntax of arrow functions makes them more compact.
					- Example:
					  ```javascript
					  const greet = (name) => `Hello, ${name}!`;
					  ```
				- Parentheses and Arrow Functions
					- If an arrow function takes exactly one parameter, parentheses around the parameter list can be omitted.
					- Example:
					  ```javascript
					  const square = num => num * num;
					  ```
				- No Arguments
					- For arrow functions with no parameters, you need to include an empty set of parentheses `()`.
					- Example:
					  ```javascript
					  const logHello = () => console.log('Hello!');
					  ```
				- Multiline Arrow Functions
					- If the function body requires more processing and needs to span multiple lines, it must be placed within brackets `{}`.
					- In such cases, explicit `return` must be used if a value is to be returned.
					- Example:
					  ```javascript
					  const greet = (name) => {
					    const message = `Hello, ${name}!`;
					    return message;
					  }
					  ```
				- `this` Keyword
					- Unlike regular functions, arrow functions do not have their own `this`. The value of `this` inside an arrow function is always inherited from the enclosing scope.
					- Example:
					  ```javascript
					  const person = {
					    name: 'John',
					    sayHello: function() {
					        setTimeout(() => {
					            console.log(`Hello, my name is ${this.name}`);
					        }, 1000);
					    }
					  };
					  
					  person.sayHello(); // logs 'Hello, my name is John' after 1 second
					  ```
				- Use Cases
					- Arrow functions are ideal when you need to maintain the context of `this`, such as inside event handlers, and when you want a short, concise function that doesn't need its own `this`, `arguments`, `super`, or `new.target`.
			- Return Statement
			  collapsed:: true
				- Functions may optionally return a value. The returned value gets substituted in the place where the function is called.
				- Example:
				  ```javascript
				  function sum(a, b) {
				    return a + b;
				  }
				  const total = sum(1, 2); // `total` is now equal to `3`
				  ```
			- Higher-Order Functions
			  collapsed:: true
				- Overview
					- Higher-order functions are a key aspect of functional programming in JavaScript. They are functions that operate on other functions, either by taking them as arguments or by returning them.
				- Functions as Arguments
					- In JavaScript, functions are first-class objects, which means they can be passed as arguments to other functions.
					- Example:
					  ```javascript
					  function greet(name) {
					    return `Hello, ${name}!`;
					  }
					  
					  function shout(fn, name) {
					    return fn(name).toUpperCase();
					  }
					  
					  console.log(shout(greet, 'John')); // logs 'HELLO, JOHN!'
					  ```
					- In the above example, the `shout` function is a higher-order function. It takes the `greet` function as an argument.
				- Functions as Return Values
					- Higher-order functions can also return other functions.
					- Example:
					  ```javascript
					  function multiplyBy(factor) {
					    return function (number) {
					        return number * factor;
					    }
					  }
					  
					  const double = multiplyBy(2);
					  console.log(double(5)); // logs '10'
					  ```
					- In the above example, the `multiplyBy` function is a higher-order function. It returns a new function that multiplies its input by the `factor` parameter.
				- Built-in Higher-Order Functions
					- JavaScript includes several built-in higher-order functions that operate on arrays, such as `map`, `filter`, and `reduce`.
					- Example:
					  ```javascript
					  const numbers = [1, 2, 3, 4, 5];
					  
					  const doubled = numbers.map(number => number * 2);
					  console.log(doubled); // logs '[2, 4, 6, 8, 10]'
					  
					  const evens = numbers.filter(number => number % 2 === 0);
					  console.log(evens); // logs '[2, 4]'
					  
					  const sum = numbers.reduce((total, number) => total + number, 0);
					  console.log(sum); // logs '15'
					  ```
			- Callback Functions
			  collapsed:: true
				- Overview
					- A callback function is a function that is passed as an argument to another function, and is executed after its parent function has completed. Callbacks are a way to make sure certain code doesn’t execute until other code has already finished execution.
				- Synchronous Callbacks
					- These are the functions that are invoked immediately. The higher-order function that uses the callback function will run the callback before finishing its own execution.
					- Example:
					  ```javascript
					  const numbers = [1, 2, 3, 4, 5];
					  
					  numbers.forEach(function(number) {
					    console.log(number);
					  });
					  ```
					- In this example, `forEach` is a higher-order function that takes a callback function. For each element in the array, `forEach` calls the callback function with the element as an argument.
				- Asynchronous Callbacks
					- These callbacks are not executed immediately. They are usually invoked in response to an event like a user interaction, an API call, or a timer.
					- Example:
					  ```javascript
					  setTimeout(function() {
					    console.log('Hello after 2 seconds');
					  }, 2000);
					  ```
					- In this example, `setTimeout` is a built-in JavaScript function that delays the execution of the callback function by a specified number of milliseconds.
				- Error-First Callbacks
					- This is a convention in Node.js, where callbacks are often used for error handling. The first argument to the callback is an error object, which is `null` if no error occurred.
					- Example:
					  ```javascript
					  fs.readFile('/path/to/file', function(err, data) {
					    if (err) {
					        console.error('An error occurred:', err);
					    } else {
					        console.log('File data:', data);
					    }
					  });
					  ```
			- Immediately Invoked Function Expressions (IIFEs)
			  collapsed:: true
				- Overview
					- An Immediately Invoked Function Expression (IIFE) is a JavaScript function that runs as soon as it is defined.
					- IIFEs are a design pattern which is also known as a Self-Executing Anonymous Function.
				- Syntax
					- The syntax of an IIFE involves defining a function enclosed in parentheses `()`, which makes it an expression, and then invoking the function with a second pair of parentheses `()`.
					- Example:
					  ```javascript
					  (function () {
					    var x = 'Hello World!';
					    console.log(x);
					  })();
					  ```
				- Scope Isolation
					- One of the primary uses of IIFEs is to isolate scope. Variables declared in an IIFE are not visible to the outside world, which helps avoid variable collisions in the global scope.
					- Example:
					  ```javascript
					  (function () {
					    var x = 'Hello World!';
					  })();
					  
					  console.log(x); // ReferenceError: x is not defined
					  ```
					- In the above example, `x` is not accessible outside the IIFE because it is not part of the global scope.
				- Use Cases
					- IIFEs are commonly used when we want to create a new scope, to avoid polluting the global scope. They're also used in JavaScript modules to encapsulate private variables and methods.
					- Another common use case is for running initialization code that should only run once.
				- Conclusion
					- IIFEs are an important pattern in JavaScript for controlling variable scope and preventing unwanted global scope pollution. They allow you to define variables and functions that don't interfere with other code, keeping your global scope clean and organized.
			- [[Closures]]
			  collapsed:: true
				- What are Closures?
					- A closure is a JavaScript function which has access to the outer (enclosing) function's variables—scope chain.
					- The closure has three scope chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables, and it has access to the global variables.
				- How do you create a Closure?
				  collapsed:: true
					- In JavaScript, a closure is created every time a function is created, at function creation time.
					- To use a closure, define a function inside another function and expose it.
					- Example:
					  ```javascript
					  function makeAdder(x) {
					    return function(y) {
					        return x + y;
					    };
					  }
					  
					  var add5 = makeAdder(5);
					  var add10 = makeAdder(10);
					  
					  console.log(add5(2));  // 7
					  console.log(add10(2)); // 12
					  ```
					- In this example, `makeAdder` is a function factory — it creates functions which can add a specific value to their argument.
				- What is Closure Scope Chain?
				  collapsed:: true
					- The inner function can access variables from the outer function, even after the outer function has finished executing.
					- The closure's scope chain includes:
						- its own scope (variables defined within its curly brackets),
						- the outer function's variables,
						- and the global variables.
				- What are the use-cases?
					- Closures are used for [[Data Privacy]] and [[Encapsulation]].
					- They're also used to create function factories and in functional programming patterns.
				- Conclusion
				  collapsed:: true
					- Closures are a powerful feature of JavaScript. They allow functions to maintain access to variables defined in their enclosing scope, even after that scope has finished executing. This allows for powerful and flexible programming patterns.
			- Bind, Call, and Apply
			  collapsed:: true
				- Overview
					- `bind`, `call`, and `apply` are all methods that can be used to change the `this` context of a function.
					- All three are built-in methods of JavaScript functions and they each allow you to invoke a function with a specific `this` context and pass in arguments in different ways.
				- Bind Method
					- The `bind` method creates a new function that, when called, has its `this` keyword set to the provided value.
					- The `bind` method also accepts additional parameters that are used as arguments to the function when the bound function is called.
					- Example:
					  ```javascript
					  var obj = { name: 'John' };
					  
					  function greet(greeting) {
					    console.log(greeting + ', ' + this.name);
					  }
					  
					  var boundGreet = greet.bind(obj, 'Hello');
					  
					  boundGreet();  // Logs "Hello, John"
					  ```
				- Call Method
					- The `call` method calls a function with a given `this` value and arguments provided individually.
					- Unlike `bind`, `call` immediately invokes the function.
					- Example:
					  ```javascript
					  var obj = { name: 'John' };
					  
					  function greet(greeting) {
					    console.log(greeting + ', ' + this.name);
					  }
					  
					  greet.call(obj, 'Hello');  // Logs "Hello, John"
					  ```
				- Apply Method
					- The `apply` method calls a function with a given `this` value and arguments provided as an array (or an array-like object).
					- Like `call`, `apply` immediately invokes the function.
					- Example:
					  ```javascript
					  var obj = { name: 'John' };
					  
					  function greet(greeting) {
					    console.log(greeting + ', ' + this.name);
					  }
					  
					  greet.apply(obj, ['Hello']);  // Logs "Hello, John"
					  ```
				- Conclusion
					- `bind`, `call`, and `apply` are powerful tools that allow you to control the context in which functions are executed in JavaScript. They can be very useful for situations where you need to control what `this` refers to.
			- Recursive Functions
			  collapsed:: true
				- A recursive function is a function that calls itself during its execution.
				- Example:
				  ```javascript
				  function factorial(x) {
				    if (x < 0) return;
				    if (x === 0) return 1;
				    return x * factorial(x - 1);
				  }
				  
				  console.log(factorial(5)); // logs 120, which is 5*4*3*2*1
				  ```
			- Conclusion
			  collapsed:: true
				- Functions are fundamental to JavaScript. They help you implement functionality multiple times, keep your code DRY (Don't Repeat Yourself), divide your code into reusable pieces, and abstract away code for task encapsulation.
	- Advanced Components of JavaScript
		- [[This]]
		  collapsed:: true
			- Overview
				- In JavaScript, the `this` keyword is a special variable that’s automatically declared by the engine.
				- The value of `this` is determined by how a function is called. It's a context pointer to the object that is currently executing the function.
			- `this` in a Method
				- When a function is called as a method of an object, `this` is set to the object the method is called on.
				- Example:
				  ```javascript
				  let car = {
				     make: 'Toyota', 
				     model: 'Camry', 
				     start: function() { 
				         console.log(this.make + ' ' + this.model + ' started.'); 
				     }
				  };
				  car.start();  // "Toyota Camry started."
				  ```
				- Here, `this` inside the `start` function is referring to the `car` object.
			- `this` in a Regular Function
				- In a regular function (not a method or an arrow function), `this` is set to the global object (`window` in a browser, `global` in Node.js). But if "use strict" is in place, `this` is `undefined`.
				- Example:
				  ```javascript
				  function myFunction() {
				     console.log(this);
				  }
				  myFunction();  // Window {...} (or global {...} in Node.js)
				  ```
			- `this` in Arrow Functions
				- In arrow functions, `this` is lexically or statically bound. It means that it doesn't matter how and where they are called, it only matters where they are defined. In arrow functions, `this` retains the value of the enclosing lexical context's `this`.
				- Example:
				  ```javascript
				  let car = {
				     make: 'Toyota', 
				     model: 'Camry', 
				     start: () => { 
				         console.log(this.make + ' ' + this.model + ' started.'); 
				     }
				  };
				  car.start();  // "undefined undefined started."
				  ```
				- Here, `this` inside the `start` function does not refer to the `car` object but to the global object, because it's an arrow function.
			- Conclusion
				- Understanding the `this` keyword is a critical part of using JavaScript effectively, especially when working with object methods and constructors.
		- [[Arrays]]
		  collapsed:: true
			- What are Arrays?
				- Arrays are a special type of objects used for storing multiple values in a single variable.
				- Each item in an array has a position, starting from `0`.
			- How do you declare an array?
				- An array can be declared in two ways:
				- Using array literal syntax:
				  ```javascript
				  let arrayName = [];
				  ```
				- Using the Array constructor:
				  ```javascript
				  let arrayName = new Array();
				  ```
			- How can you access Array Elements?
				- Array elements are accessed using their index number:
				  ```javascript
				  let fruits = ['apple', 'banana', 'cherry'];
				  console.log(fruits[0]); // Logs 'apple'
				  ```
			- What methods are there for Arrays?
				- Arrays in JavaScript come with a variety of methods. Some of the most commonly used ones include the following:
				- `push()`: adds a new element to the end of the array.
				- `pop()`: removes the last element from the array.
				- `shift()`: removes the first element from the array.
				- `unshift()`: adds a new element to the beginning of the array.
				- `splice()`: adds/removes items to/from an array, and returns the removed item(s).
				- `slice()`: selects a part of an array, and returns the new array.
				- `concat()`: merges two or more arrays, and returns result.
				- `join()`: joins all elements of an array into a string.
			- What are Multi-Dimensional Arrays?
				- A multi-dimensional array is an array of arrays. It's a way of storing tables of values, where each row is an array and each cell in the row is an element of the array.
				- Declaring Multi-Dimensional Arrays
					- You can declare a multi-dimensional array the same way you declare a one-dimensional array.
					- Example:
					  ```javascript
					  let matrix = [
					    [1, 2, 3],
					    [4, 5, 6],
					    [7, 8, 9]
					  ];
					  ```
				- Accessing Elements in Multi-Dimensional Arrays
					- Elements in a multi-dimensional array are accessed by using two or more sets of square brackets.
					- Example:
					  ```javascript
					  let matrix = [
					    [1, 2, 3],
					    [4, 5, 6],
					    [7, 8, 9]
					  ];
					  
					  console.log(matrix[0][1]); // Logs 2
					  ```
				- Modifying Elements in Multi-Dimensional Arrays
					- You can modify elements of a multi-dimensional array in a similar way to how you access them.
					- Example:
					  ```javascript
					  let matrix = [
					    [1, 2, 3],
					    [4, 5, 6],
					    [7, 8, 9]
					  ];
					  
					  matrix[1][2] = 10; // Modifies the element at second row and third column
					  ```
				- Conclusion
					- Multi-dimensional arrays in JavaScript allow for the storage and manipulation of complex, structured data. They're a vital tool for a variety of tasks including the handling of sets of data points, game boards, simulations, and more.
			- Conclusion
				- Arrays in JavaScript provide a way to store multiple values in a single variable. They come with many built-in methods that make it easy to manipulate and iterate over the data.
		- [[Events]]
		  collapsed:: true
			- Overview
			  collapsed:: true
				- JavaScript's interactivity is made possible by events. An event is a signal that something has occurred (like a user clicking a button or the page finishing loading).
				- Each event is associated with a certain element, and can be used to create an interactive web experience for users.
			- Common Types of Events
			  collapsed:: true
				- `click`: The event occurs when an element is clicked.
				- `load`: The event occurs when a page has finished loading.
				- `mouseover`: The event occurs when the mouse pointer is moved onto an element.
				- `mouseout`: The event occurs when the mouse pointer is moved out of an element.
				- `keydown`: The event occurs when a keyboard key is pressed down.
				- `keyup`: The event occurs when a keyboard key is released.
			- Event Listeners
			  collapsed:: true
				- Overview
					- Events are actions or occurrences that happen in the browser controlled by a user, which can be detected by JavaScript.
				- Adding Event Listeners
				  collapsed:: true
					- To react to an event, we can attach a function to an event handler on a specific element using the `addEventListener()` method.
					- The `addEventListener()` method takes two arguments: the name of the event we want to respond to, and the function that gets called when the event occurs.
					- Example:
					  ```javascript
					  let btn = document.querySelector('button');
					  btn.addEventListener('click', function() {
					  alert('Button was clicked!');
					  });
					  ```
				- Removing Event Listeners
				  collapsed:: true
					- Overview
						- Removing event listeners is important for performance reasons, especially when you have a lot of them and/or they are no longer needed.
					- `removeEventListener`
						- The `removeEventListener` method is used to remove an event listener that was previously added with `addEventListener`.
						- It takes the same arguments as `addEventListener`: the event to stop listening for, and the function to stop calling when the event occurs.
						- You must pass in the exact same function to `removeEventListener` as you passed into `addEventListener`. This means that you cannot use anonymous functions as event listeners if you ever intend to remove them.
						- Example:
						  ```javascript
						  let button = document.querySelector('button');
						  function greet() {
						    alert('Hello, World!');
						  }
						  button.addEventListener('click', greet);
						  // ...some time later...
						  button.removeEventListener('click', greet);
						  ```
				- Event Propagation
				  collapsed:: true
					- What is Event Propagation?
						- The process of handling events in the DOM involves three phases: capturing, target, and bubbling.
						- In the capturing phase, the event travels down from the `document` to the target element.
						- At the target phase, the event has reached the target element.
						- In the bubbling phase, the event bubbles up from the target element back to the `document`.
					- What is the Event Flow?
						- When an event occurs on a DOM element, that event does not entirely occur on just that one element. In the browsers' event system, the event actually occurs on every node from the root of the document to the deepest child node (and back), and it passes through the element that you've actually clicked.
					- Capturing Phase
						- During the capturing phase, the event moves from the `document` to the target element.
						- It goes down the hierarchy, starting from the topmost `document` object and triggering any capturing event listeners on its way down to the target element.
						- This phase is used less frequently than the other two phases.
					- Target Phase
						- During the target phase, the event reaches the target element, and any event listeners added to the specific element with the same event type are triggered.
					- Bubbling Phase
						- During the bubbling phase, the event bubbles up from the target element to the `document`.
						- It triggers any event listeners along the way up that are waiting for the event to happen.
						- Most common event handling is done during this phase.
						- By default, event handlers are executed in the bubbling phase. However, you can set an event handler to the capturing phase by setting the third argument to `addEventListener()` to `true`.
					- Stopping Propagation
						- The event's propagation can be stopped at any point, including during the capturing and bubbling phases.
						- The `stopPropagation()` method is used to prevent further propagation of an event during event capturing and bubbling.
						- However, use this method with caution, as it can often have unintended consequences. For instance, it can prevent other legitimate event handlers from being triggered.
					- Event Propagation and `addEventListener()`
						- When you use `addEventListener()`, you can specify the phase where you want the listener to be triggered.
						- By default, the `addEventListener()` method handles events during the bubbling phase.
						- However, you can set the third argument of `addEventListener()` to `true` to handle an event during the capturing phase.
					- What is an example?
						- ```javascript
						  // Capturing phase
						  document.body.addEventListener('click', () => {
						  console.log('document body click - Capturing phase');
						  }, true); 
						  
						  // Bubbling phase
						  document.body.addEventListener('click', () => {
						  console.log('document body click - Bubbling phase');
						  }, false); 
						  
						  // Stop Propagation
						  document.getElementById('myButton').addEventListener('click', (event) => {
						  event.stopPropagation();
						  });
						  ```
				- Preventing Default Behavior
				  collapsed:: true
					- Overview
						- Many HTML elements have default behaviors associated with them. For example, clicking on a hyperlink navigates to a new URL, and submitting a form sends a POST request to the server.
						- In JavaScript, we can prevent these default behaviors from occurring using the `preventDefault()` method on the event object.
					- `preventDefault()`
						- `preventDefault()` is a method that can be called on the event object in an event listener.
						- When this method is invoked, it prevents the default action associated with the event from occurring.
						- This is useful when you want to handle events in JavaScript without letting the browser execute the default action.
						- This does not stop the event from bubbling up through the DOM. It simply prevents the default action.
					- Examples of Preventing Default Behavior
						- Below are some examples where preventing default behavior is useful:
						- 1. **Form Submission**: By default, when a form is submitted, the page reloads and form data is sent to the server. However, you might want to validate the form data or handle the submission via JavaScript, and thus, would need to prevent the default form submission behavior.
						  ```javascript
						  document.querySelector('form').addEventListener('submit', function(event) {
						  	event.preventDefault();
						  	// Validate form data and handle submission
						  });
						  ```
						- 2. **Hyperlink Navigation**: Clicking a hyperlink navigates to a new URL. However, you might want to handle the click event in your JavaScript code and prevent the default navigation behavior.
						  ```javascript
						  document.querySelector('a').addEventListener('click', function(event) {
						  	event.preventDefault();
						  	// Handle click event
						  });
						  ```
					- Conclusion
						- The `preventDefault()` method is an important tool in JavaScript programming. It provides control over the default behaviors of HTML elements, and allows more complex event handling and interaction design.
				- Event Object
				  collapsed:: true
					- Overview
						- When an event occurs, the event listener function is called and an event object is passed to it as an argument. This object contains properties and methods related to the event.
					- Properties of the Event Object
						- `target`: The element that triggered the event.
						- `type`: The type of the event (like "click", "keydown", etc.).
						- `bubbles`: A boolean indicating whether the event bubbles up through the DOM or not.
					- Preventing Default Behavior
						- The event object has a method called `preventDefault()` that can be used to stop the default action of the element from happening.
						- For example, it can prevent a link from being followed or a form from being submitted.
			- Event Delegation
			  collapsed:: true
				- What is Event Delegation?
					- Event delegation is a technique in JavaScript where you delegate listening for an event to a parent element, instead of listening for the event on the element it originates from (the target element).
					- This is possible due to the nature of event propagation in the DOM, where events bubble up (or propagate) from the target element through its ancestors in the DOM tree.
					- This technique can improve performance, particularly when dealing with a large number of similar elements.
				- What are the benefits?
					- **Performance**: Instead of attaching many event listeners to individual elements, you attach a single event listener to a parent element. This can be a significant performance improvement for pages with many elements.
					- **Dynamic Elements**: If elements are added or removed dynamically, you don't have to attach or detach event listeners, as the listener is on the parent.
					- **Lower Memory Footprint**: Since only one event listener is attached to the parent element instead of attaching to each child, it results in less memory usage.
				- How can you implement Event Delegation?
					- You implement event delegation by adding an event listener to a parent element. In the listener's function, you use the event object's `target` property to determine which element originally dispatched the event.
					- Here is an example:
					  ```javascript
					  document.querySelector('#parent-element').addEventListener('click', function(event) {
					  const clickedElement = event.target;
					  
					  if (clickedElement.matches('.child-element')) {
					  console.log('A child element was clicked!');
					  // Perform your action
					  }
					  });
					  ```
					- In the example, a click event listener is attached to an element with the id `parent-element`. When a click event is triggered, it checks if the target of the event is a child element with the class `child-element`. If so, it logs a message and performs the desired action.
				- Conclusion
					- Event delegation is an important technique for handling events efficiently in JavaScript. It is particularly useful when dealing with dynamic elements or large lists, where attaching individual event listeners could affect performance.
			- Event Loop
			  collapsed:: true
				- What is an Event Loop?
					- The Event Loop is a process in the JavaScript runtime environment that handles the execution of multiple chunks of your program, each piece being an individual operation that's relatively small.
					- The Event Loop enables JavaScript to be non-blocking and asynchronous by constantly monitoring the Call Stack and the Callback Queue. If the Call Stack is empty, it takes the first event from the queue and pushes it to the Call Stack, which starts to execute it.
				- What are the components?
					- **Call Stack**: It's a data structure which records where in the program we are. If we step into a function, we put (push) it on to the stack, and when we return from a function, we pop off the top of the stack.
					- **Heap**: This is an unstructured region of memory used for the allocation of objects and variables created during the runtime of your application.
					- **Callback Queue/Task Queue**: It's a list of all the operations that are waiting to be executed because they were pushed off the Call Stack due to being asynchronous and non-blocking (like setTimeout, user interactions, or AJAX requests).
				- How does it work?
					- When a script calls a function, the function is added to the Call Stack.
					- If that function calls another function, that function is added to the Call Stack and so on.
					- When a function completes, it is removed from the Call Stack.
					- If the Call Stack is empty, the Event Loop will take the first task from the Callback Queue and will push it to the Call Stack, which starts to execute it.
					- This cycle continues indefinitely until there are no more code snippets to execute, which usually happens when a user closes the page/browser.
				- Conclusion
					- The Event Loop is an essential part of JavaScript as it enables non-blocking, asynchronous behavior. This allows JavaScript applications to be responsive and efficient, despite JavaScript being single-threaded.
			- Event Handling
			  collapsed:: true
				- What is Event Handling?
					- Events are the actions or occurrences that happen in the browser while you are browsing, they can be caused by users or the browser itself. Examples of events include clicking a button, pressing a key, resizing a window, submitting a form, etc.
					- Event handling in JavaScript involves three main steps: creating an event handler, attaching the event handler to an event, and writing code that will be executed when the event occurs.
				- How to create an Event Handler?
					- An event handler in JavaScript is a [[Function]] that deals with an event when it occurs. This function contains the code that will be executed when the event happens.
					- For example:
					  ```javascript
					  function handleClick(event) {
					  alert('You clicked the button!');
					  }
					  ```
				- How to attach an Event Handler to an Event?
					- Once the event handler function is created, it needs to be attached to an event using `addEventListener()`.
					- The `addEventListener()` method takes two arguments: the event type (e.g., 'click') and the event handler function.
					- For example:
					  ```javascript
					  const button = document.querySelector('button');
					  button.addEventListener('click', handleClick);
					  ```
				- How to remove Event Handlers?
					- You can also remove an event handler that has been attached to an event using `removeEventListener()`.
					- The `removeEventListener()` method takes the same arguments as `addEventListener()`.
					- For example:
					  ```javascript
					  button.removeEventListener('click', handleClick);
					  ```
				- What are inline Event Handlers?
					- Although not commonly used due to concerns around separation of concerns and scalability, you can also define event handlers inline in the HTML.
					- For example:
					  ```html
					  <button onclick="alert('You clicked the button!');">Click me</button>
					  ```
				- Conclusion
					- Event handling is a fundamental part of JavaScript and allows us to create interactive and dynamic web pages. By using event handlers, we can control how our web page responds to different actions performed by a user or the browser.
			- Conclusion
			  collapsed:: true
				- Events are a crucial part of JavaScript programming as they enable the interaction between the user and the webpage. By understanding how to use events, you can create dynamic and interactive web experiences.
		- Promises and Async/Await
		  collapsed:: true
			- What are Promises and Async Await?
			  collapsed:: true
				- Promises and async/await are two built-in ways in JavaScript to handle asynchronous operations.
				- They allow us to handle operations that take time to complete without blocking the rest of the code.
			- [[Promises]]
			  collapsed:: true
				- What is a Promise?
				  collapsed:: true
					- A Promise is an object in JavaScript that links the producing code (the code that does something asynchronously) and the consuming code (the code that wants the result of the asynchronous operation) together.
					- A Promise represents an operation that hasn't completed yet but is expected to in the future.
				- What are the Promise States?
				  collapsed:: true
					- A Promise is always in one of these states:
					- **Pending:** initial state, neither fulfilled nor rejected.
					- **Fulfilled:** the operation completed successfully.
					- **Rejected:** the operation failed.
				- How to create a promise?
				  collapsed:: true
					- Promise Constructor
					  collapsed:: true
						- Promises are created using the `Promise` constructor. It takes a single argument, an executor function.
						- The executor function itself takes two parameters, usually named `resolve` and `reject`.
						- `resolve` is a function to call when the promise should be resolved, while `reject` is a function to call when the promise should be rejected.
						- Here's an example:
						  ```javascript
						  let myFirstPromise = new Promise((resolve, reject) => {
						  // Some asynchronous operation...
						  });
						  ```
					- Resolving a Promise
					  collapsed:: true
						- When an asynchronous operation completes successfully, you would call `resolve` with the resulting value.
						- This marks the promise as fulfilled and makes the value available to any `.then` handlers.
						- Here's an example:
						  ```javascript
						  let myFirstPromise = new Promise((resolve, reject) => {
						  setTimeout(function() {
						    resolve("Success!");  // Yay! Everything went well!
						  }, 250);
						  });
						  ```
					- Rejecting a Promise
					  collapsed:: true
						- If an error occurs during the asynchronous operation, you would call `reject` with the error.
						- This marks the promise as rejected and passes the error to any `.catch` handlers.
						- Here's an example:
						  ```javascript
						  let myFirstPromise = new Promise((resolve, reject) => {
						  setTimeout(function() {
						    reject("Failed!");  // Oh no, something went wrong!
						  }, 250);
						  });
						  ```
				- How can you use a Promise?
				  collapsed:: true
					- Overview
					  collapsed:: true
						- After creating a Promise, it can be used to manage asynchronous code execution.
						- Promises have methods (like `.then()`, `.catch()`, and `.finally()`) that are used to handle the fulfilled or rejected state.
					- `.then()`
					  collapsed:: true
						- The `.then()` method is called when the Promise is fulfilled.
						- It takes a callback function, which will be invoked with the value passed to `resolve()`.
						- Here's an example:
						  ```javascript
						  let myFirstPromise = new Promise((resolve, reject) => {
						  setTimeout(function() {
						    resolve("Success!");  
						  }, 250);
						  });
						  
						  myFirstPromise.then((successMessage) => {
						  console.log("Yay! " + successMessage);
						  });
						  ```
					- Chaining `.then()`
					  collapsed:: true
						- You can chain `.then()` methods, creating a series of asynchronous steps.
						- Each `.then()` returns a new Promise that's fulfilled by the return value of its callback.
						- Here's an example:
						  ```javascript
						  myFirstPromise
						  .then(step1)
						  .then(step2)
						  .then((finalResult) => {
						  console.log(finalResult);
						  });
						  ```
					- `.catch()`
					  collapsed:: true
						- The `.catch()` method is called when the Promise is rejected.
						- It takes a callback function, which will be invoked with the error passed to `reject()`.
						- Here's an example:
						  ```javascript
						  let myFirstPromise = new Promise((resolve, reject) => {
						  setTimeout(function() {
						    reject("Failed!");  
						  }, 250);
						  });
						  
						  myFirstPromise.catch((errorMessage) => {
						  console.log("Oops! " + errorMessage);
						  });
						  ```
					- `.finally()`
					  collapsed:: true
						- The `.finally()` method is called when the Promise is settled, whether fulfilled or rejected.
						- It is often used for cleanup or releasing resources, regardless of the outcome.
						- Here's an example:
						  ```javascript
						  myFirstPromise.finally(() => {
						  console.log("Promise settled!");
						  });
						  ```
					- Conclusion
					  collapsed:: true
						- Using a Promise involves chaining `.then()` to handle successful asynchronous operations, `.catch()` to handle errors, and `.finally()` to execute code after the Promise is settled.
						- This pattern makes it easier to write and reason about asynchronous code in JavaScript.
				- What is Chaining Promises?
				  collapsed:: true
					- What is Chaining Promises?
						- Chaining is a technique used to simplify the handling of asynchronous operations in JavaScript.
						- The Promise returned by the `.then()` method allows for creating a sequence of asynchronous operations that run one after the other.
					- What's the process?
						- Each `.then()` method returns a new Promise.
						- If the callback in `.then()` returns a value, the Promise gets resolved with that value.
						- If the callback in `.then()` returns a new Promise, the next `.then()` in the chain will wait until that Promise is settled.
					- Example of Chaining Promises
						- Here's an example of how Promise chaining can be used:
						  ```javascript
						  let promise = new Promise((resolve, reject) => {
						  setTimeout(() => resolve(1), 1000); // Initial promise that resolves to 1 after 1 second
						  });
						  
						  promise
						  .then((result) => {
						    console.log(result); // Logs 1
						    return result * 2; // Returns a direct value
						  })
						  .then((result) => {
						    console.log(result); // Logs 2
						    return new Promise((resolve, reject) => {
						      setTimeout(() => resolve(result * 2), 1000); // Returns a new Promise that resolves after 1 second
						    });
						  })
						  .then((result) => {
						    console.log(result); // Logs 4 after waiting for the previous Promise to resolve
						  });
						  ```
					- Error Handling in Chaining
						- If an error occurs in any `.then()` in the chain, execution jumps to the nearest `.catch()` handler down the chain.
						- Here's an example:
						  ```javascript
						  promise
						  .then((result) => {
						    throw new Error('Something failed');
						    return result * 2;
						  })
						  .catch((error) => {
						    console.log(error); // Catches and logs the error
						  });
						  ```
					- Conclusion
						- Chaining promises allows for a more readable and manageable way to organize asynchronous code in JavaScript.
						- It's essential to handle errors in the chain to prevent silent failures.
				- `Promise.all` and `Promise.race`
				  collapsed:: true
					- `Promise.all` is used when you want to execute multiple Promises in parallel and wait until all of them are ready.
					- `Promise.race` is used when you want to execute multiple Promises in parallel and wait until the first one is ready.
				- Conclusion
				  collapsed:: true
					- Promises are a very powerful concept for managing asynchronous operations in JavaScript. They allow you to structure your code in a much more readable and maintainable way.
			- [[Async Await]]
			  collapsed:: true
				- What is Async Await?
				  collapsed:: true
					- Async/Await, introduced in ES2017, is syntactic sugar on top of Promises and allows you to work with Promises in a more readable and elegant way.
					- It makes asynchronous code look and behave a little more like synchronous code, improving readability.
				- What are Async Functions?
				  collapsed:: true
					- An `async` function is a function declared with the `async` keyword.
					- Async functions are instances of the `AsyncFunction` constructor, and the `await` keyword is permitted within them.
					- Although `async` functions return a Promise by default, the resolution value of the Promise will be the return value of the `async` function.
					- Here's an example:
					  ```javascript
					  async function foo() {
					  return 1;
					  }
					  ```
				- What is the Await Keyword?
				  collapsed:: true
					- The `await` keyword is used in an `async` function to pause the execution of the function and wait for a Promise's resolution or rejection.
					- The `await` keyword can only be used inside an `async` function.
					- Here's an example:
					  ```javascript
					  async function foo() {
					  let promise = new Promise((resolve, reject) => {
					    setTimeout(() => resolve("done!"), 1000)
					  });
					  
					  let result = await promise; // wait until the promise resolves
					  console.log(result); // "done!"
					  }
					  ```
				- [[Error Handling]]
				  collapsed:: true
					- Overview
					  collapsed:: true
						- Error handling is an important aspect of writing robust code, especially when dealing with asynchronous operations.
						- JavaScript provides mechanisms to handle errors both in Promises and Async/Await.
					- Error Handling in Promises
					  collapsed:: true
						- Promises use `.catch` method to handle errors.
						- The `.catch` handler is called when a promise is rejected or an error is thrown in the executor function.
						- The rejected value or error is passed as an argument to the `.catch` handler.
						- Here's an example:
						  ```javascript
						  let promise = new Promise(function(resolve, reject) {
						  throw new Error("An error occurred!");
						  });
						  
						  promise.catch(function(error) {
						  console.log(error);  // "An error occurred!"
						  });
						  ```
					- Unhandled Promise Rejections
					  collapsed:: true
						- If a promise is rejected but there is no `.catch` handler, it will result in an unhandled promise rejection.
						- You can handle these globally using the `unhandledrejection` event.
						  ```javascript
						  window.addEventListener('unhandledrejection', function(event) {
						  console.log(event.promise);  // Promise that was rejected
						  console.log(event.reason);  // Reason of the rejection
						  });
						  ```
					- Error Handling in Async/Await
					  collapsed:: true
						- In Async/Await, errors are handled using traditional `try...catch` blocks.
						- `try` encloses the code that may cause an error, and `catch` defines what to do when an error occurs.
						- Here's an example:
						  ```javascript
						  async function foo() {
						  try {
						    let response = await fetch('http://no-such-url');
						  } catch(err) {
						    console.log(err); // TypeError: Failed to fetch
						  }
						  }
						  ```
					- Async/Await with finally
					  collapsed:: true
						- Like promises, async/await also has a `finally` clause that runs whether the promise is resolved or rejected.
						- `finally` is a good place to handle cleanup tasks.
						- Here's an example:
						  ```javascript
						  async function foo() {
						  try {
						    let response = await fetch('http://no-such-url');
						  } catch(err) {
						    console.log(err); // TypeError: Failed to fetch
						  } finally {
						    console.log('Cleanup tasks');
						  }
						  }
						  ```
					- Conclusion
					  collapsed:: true
						- Proper error handling is crucial when dealing with Promises and Async/Await to prevent your program from failing unpredictably. It provides a way to manage and recover from errors during execution.
				- Promise.all()
				  collapsed:: true
					- What is Promise.all?
						- The `Promise.all()` method is used for executing multiple promises concurrently.
						- It returns a single Promise that resolves when all of the passed promises have resolved or when any promise has rejected.
						- This feature can be combined with Async/Await for simpler and more readable code.
					- How to use Promise.all?
						- Promise.all() takes an iterable (like an array) of promises and returns a single Promise.
						- The returned promise resolves to an array of the results of the input promises, preserving their order.
						- If any promise rejects, then the returned promise is immediately rejected with that reason.
						- Here's an example:
						  ```javascript
						  let promise1 = Promise.resolve('Hello');
						  let promise2 = 42;
						  let promise3 = new Promise((resolve, reject) => {
						  setTimeout(resolve, 100, 'World');
						  });
						  
						  Promise.all([promise1, promise2, promise3]).then((values) => {
						  console.log(values);  // ["Hello", 42, "World"]
						  });
						  ```
					- How to use Async Await with Promise.all?
						- Async/Await can be combined with Promise.all() to write asynchronous code that looks synchronous.
						- It makes it easier to handle the resolution or rejection of multiple promises together.
						- Here's an example:
						  ```javascript
						  async function foo() {
						  let promise1 = new Promise((resolve, reject) => { setTimeout(resolve, 1000, 'Hello') });
						  let promise2 = new Promise((resolve, reject) => { setTimeout(resolve, 1000, 'World') });
						  
						  let results = await Promise.all([promise1, promise2]); // Array ["Hello", "World"]
						  console.log(results);
						  }
						  
						  foo();
						  ```
					- Error Handling
						- If any promise passed to `Promise.all()` rejects, the returned promise immediately rejects with that error.
						- To handle these rejections, you can wrap `Promise.all()` in a `try...catch` block when using Async/Await.
						- Here's an example:
						  ```javascript
						  async function foo() {
						  try {
						    let results = await Promise.all([promise1, promise2, promise3]);
						    console.log(results);
						  } catch (err) {
						    console.log(err);
						  }
						  }
						  
						  foo();
						  ```
					- Conclusion
						- `Promise.all()` with Async/Await allows you to handle multiple promises together in a way that is cleaner and easier to reason about. It is especially useful when you need to perform multiple independent asynchronous tasks concurrently.
				- Conclusion
				  collapsed:: true
					- Async/Await provides a simpler and more concise way to handle Promises. It improves code readability and allows for better error handling compared to Promises alone.
			- Conclusion
			  collapsed:: true
				- Promises and async/await are powerful tools for dealing with asynchronous operations in JavaScript. They provide ways to handle asynchronous operations in a more manageable and readable manner.
		- [[Closures]]
		  collapsed:: true
			- Overview
				- In JavaScript, a closure is a function that has access to its own scope, the outer function's scope, and the global scope.
				- Closures are created every time a function is created, at function creation time.
			- Closure Characteristics
				- A closure gives you access to an outer function’s scope from an inner function.
				- In JavaScript, closures are created every time a function is created.
			- Why Closures
				- Closures are used for data privacy and encapsulation.
				- They can also be used to create stateful functions; functions that hold state.
			- Example of a Closure
				- Here's a simple example of a closure:
				  ```javascript
				  function outerFunction(outerVariable) {
				  return function innerFunction(innerVariable) {
				    console.log('outerVariable:', outerVariable);
				    console.log('innerVariable:', innerVariable);
				  }
				  }
				  const newFunction = outerFunction('outside');
				  newFunction('inside'); // Logs: outerVariable: outside, innerVariable: inside
				  ```
				- In this example, `innerFunction` is a closure that is accessing outerVariable from its parent scope.
			- Closures and Loops
				- Overview
					- Closures in loops can be a tricky concept in JavaScript due to the way closures preserve the value of variables.
					- When we create a function inside a loop and store references to loop variables inside the function, the closures do not close over the loop variable itself but over the whole variable environment.
				- Common Mistake
					- A common mistake occurs when creating functions within a loop, which rely on the loop's index.
					- Due to the nature of closures, these functions do not capture the current loop index, but rather the final value the loop index reaches.
					- This results in each function referencing the final index value, not the value at the time the function was created.
					- Here's an example that illustrates the issue:
					  ```javascript
					  for (var i = 1; i <= 5; i++) {
					  setTimeout(function timer() {
					    console.log(i);
					  }, i * 1000);
					  }
					  ```
					- This will print "6" five times, not "1", "2", "3", "4", "5" as might be expected. This is because the functions are closures over the same environment where `i` is declared, and by the time the `setTimeout` functions are executed, the loop has already finished and `i` has a value of 6.
				- Solutions
					- To solve this issue, you can use the `let` keyword, which creates a new variable environment for each loop iteration.
					- Here's the corrected example using `let`:
					  ```javascript
					  for (let i = 1; i <= 5; i++) {
					  setTimeout(function timer() {
					    console.log(i);
					  }, i * 1000);
					  }
					  ```
					- This will correctly print "1", "2", "3", "4", "5", each number printed one second after the previous.
				- Conclusion
					- Understanding how closures work with loops is key to avoiding common mistakes and bugs. With the correct use of closures, you can harness the full power of JavaScript to write cleaner, more efficient code.
			- Conclusion
				- Understanding closures is key to understanding how JavaScript works. They are powerful tools that keep variables alive even after the outer function has returned.
		- Prototypes and Inheritance
			- Overview
				- In JavaScript, objects have a special hidden property `Prototype` (also known as "proto"), that is either null or references another object. That object is called "a prototype".
				- When we read a property from object, and it’s missing, JavaScript automatically takes it from the prototype.
			- Prototype Chains
				- Overview
					- Prototype chaining (or prototypal inheritance) is a feature unique to JavaScript. It is JavaScript's mechanism for inheritance.
					- When a method (or property) is called on an object, JavaScript will try to find this method (or property) on the object itself. If it cannot find it, it will look up to the object's prototype.
				- How It Works
					- Each object in JavaScript has an internal link to another object, its prototype. That object has its own prototype, and so on, forming a chain.
					- The chain ends with `null`. `null` has no prototype, so it's the end of the chain.
				- Example
					- For instance, if you create an array `let arr = [1, 2, 3]`, the prototype chain looks like this: `arr -> Array.prototype -> Object.prototype -> null`.
					- When you call a method like `arr.join()`, JavaScript first looks for it in `arr`. Since `arr` doesn't have a `join` method, JavaScript moves up the chain to `Array.prototype` where it does find the `join` method.
				- `__proto__` Property
					- While `Prototype` is hidden, there's a property `__proto__` that allows us to get or set the prototype. However, it is considered better to use `Object.getPrototypeOf()` and `Object.setPrototypeOf()` to get and set the prototype.
				- Conclusion
					- Understanding prototype chains is key to understanding how JavaScript works. It's an essential part of the language and how objects inherit features from one another.
			- The `prototype` property
				- The `prototype` property is only used by the `new` operator. When a new object is created with `new Func()`, the object’s `Prototype` is set to `Func.prototype`.
			- Inheritance
				- JavaScript objects are dynamic "bags" of properties. JavaScript languages allows us to copy the methods from one object to another via prototypes.
				- All objects in JavaScript are instances of `Object` which sits on the top of a prototype chain.
			- Example of Inheritance
				- Here's an example of setting up inheritance between two types of objects:
				  ```javascript
				  function Animal (name) {
				  this.name = name;
				  }
				  
				  Animal.prototype.speak = function () {
				  console.log(this.name + ' makes a noise.');
				  }
				  
				  function Dog (name) {
				  Animal.call(this, name);
				  }
				  
				  Dog.prototype = Object.create(Animal.prototype);
				  
				  var dog = new Dog('Mitzie');
				  dog.speak(); // Mitzie makes a noise.
				  ```
				- In this example, `Dog` is a type of `Animal`, so we create an instance of `Animal` when creating a `Dog`, and set up the prototype to point to `Animal`'s prototype.
			- Conclusion
				- Prototypes are a fundamental part of JavaScript. They are used for defining default values, simulating class-based inheritance, and improving performance by sharing properties and methods across instances.
		- Modules
			- JavaScript modules are reusable pieces of code that can be exported from one program and imported for use in another program.
			- They help in maintaining the code, managing the code dependencies, and in code reuse.
	- Additional Components of JavaScript
		- Error Handling
			- JavaScript provides mechanisms to handle runtime errors using 'try', 'catch', and 'finally' blocks.
			- This allows for the creation of robust code that can respond to and recover from unexpected situations.
		- Regular Expressions
			- A powerful tool for working with strings, enabling complex searching, pattern matching, and replacing.
			- It's used in form validations, text parsing, and more.
		- Timers
			- Features that execute a piece of code at set intervals or after a specified delay.
			- These are accomplished through 'setTimeout', 'setInterval', and 'requestAnimationFrame'.
		- Document Object Model (DOM)
			- An API for interacting with HTML and XML documents.
			- Allows JavaScript to dynamically alter the content and structure of a webpage.
		- Fetch API and AJAX
			- Used to make HTTP requests to servers and fetch resources asynchronously.
			- These allow for dynamic loading of content without refreshing the webpage.
		- Local Storage and Session Storage
			- Web storage objects that store data persistently or for the duration of the session respectively.
			- They are used for storing and retrieving data on the client side.
		- JSON (JavaScript Object Notation)
			- A lightweight data-interchange format that is easy to read and write.
			- It is often used when data is sent from a server to a web page.
		- ES6+ Features
			- Later versions of JavaScript (commonly referred to as ES6 and beyond) have introduced a wealth of new features like classes, template strings, destructuring, arrow functions, spread and rest operators, and much more.
	- How JavaScript Works
		- JavaScript code is loaded by a web browser and interpreted line by line.
		- Variables are used to store and manipulate data while operators are used to perform operations on this data.
		- Control structures dictate the order in which these operations are performed.
		- Functions allow for reusable code that can be called anywhere within the script.
		- The end result is typically some form of interaction or dynamic content on the web page.
	- Importance of JavaScript
		- JavaScript is one of the three fundamental technologies of the web, alongside HTML and CSS.
		- It allows for the creation of rich, interactive web experiences, and is used in virtually every modern website.
		- Despite being primarily a client-side language, JavaScript can also be used server-side via Node.js, making it a versatile language for web development.
	- Conclusion
		- JavaScript is a dynamic, high-level programming language essential for modern web development. By understanding its basic building blocks, one can begin to create interactive, engaging web experiences.