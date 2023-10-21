# Error_Handling_And_ProtoType_JavaScript_Assignment


Ques  1. Type Conversion.

Ans  Type conversion in JavaScript refers to the process of changing the data type of a value from one type to another. JavaScript provides several methods and operators for performing type conversion. There are two main types of type conversion: implicit (coercion) and explicit (manual) type conversion.

1 Implicit Type Conversion (Coercion):

Implicit type conversion happens automatically when JavaScript attempts to perform operations between values of different types. For example, when you use the + operator to add a string and a number, JavaScript implicitly converts the number to a string and concatenates them:

const stringNum = "5";
const number = 10;

const result = stringNum + number; // Implicit conversion to a string
console.log(result); // "510"


In this example, the number 10 is implicitly converted to a string and concatenated with the string "5".

1 Explicit (Manual) Type Conversion:


Explicit type conversion allows you to explicitly specify the type you want to convert a value to. JavaScript provides functions and operators for explicit type conversion:

parseInt() and parseFloat(): Converts a string to an integer or a floating-point number.

const stringNum = "42";
const number = parseInt(stringNum);
console.log(number); // 42

String(): Converts a value to a string.

const number = 42;
const str = String(number);
console.log(str); // "42"

Number(): Converts a value to a number.
const str = "42";
const number = Number(str);
console.log(number); // 42

Boolean(): Converts a value to a boolean.

const value = "Hello";
const bool = Boolean(value);
console.log(bool); // true

toString(): Converts a value to a string.

const number = 42;
const str = number.toString();
console.log(str); // "42"

JSON.parse(): Parses a JSON-formatted string into a JavaScript object.

It's important to be aware of the potential risks and issues related to type conversion, especially when dealing with different data types. Improper type conversion can lead to unexpected results or errors in your code. It's a good practice to use explicit type conversion when the data type is critical to your application's logic.

Ques 2 Building Robust Functions in JavaScript

Ans  Building robust functions in JavaScript is essential for creating maintainable and reliable code. Robust functions are less prone to errors and can handle different scenarios and inputs effectively. Here are some tips for building robust functions in JavaScript:

1 Clear and Self-Explanatory Names:

Choose descriptive and meaningful names for your functions. The name should reflect the function's purpose and what it does.

2 Use Parameters:

Pass necessary data to your functions as parameters. Avoid relying on global variables or variables outside the function's scope.

3 Parameter Validation:

Check the validity of function parameters. Ensure they are of the expected type and within acceptable ranges.
Use conditional statements, assertions, or validation functions to validate parameters.

4 Return Values:

Return meaningful values from your functions. Consider what the function should return, and document it clearly.

5 Error Handling:

Implement error handling to gracefully handle unexpected situations or invalid inputs. Use try...catch blocks for this purpose.

function robustFunction(x, y) {
  try {
    if (typeof x !== 'number' || typeof y !== 'number') {
      throw new Error('Both parameters should be numbers.');
    }
    // Rest of the function logic
    return x + y;
  } catch (error) {
    // Handle the error gracefully
    console.error(error.message);
    return null;
  }
}

Comments and Documentation:

Add comments to explain complex or non-obvious parts of your code. Document your function's purpose, parameters, and expected behavior.

1 Modularity:

Keep your functions small and focused on a single task. If a function becomes too long or complex, consider breaking it into smaller, more manageable functions.

2 Avoid Side Effects:

Minimize side effects within functions. Side effects are changes to variables or state outside of the function scope, which can lead to unexpected behavior.

3 Use Default Parameters:

Take advantage of default function parameters to provide sensible default values when not all parameters are provided.

function greet(name = 'Guest') {
  return `Hello, ${name}!`;
}

1 Avoid Global Variables:

Minimize the use of global variables within your functions. If a function relies on external data, consider passing it as a parameter.

2 Testing:

Write unit tests for your functions to ensure they work as expected. Testing frameworks like Mocha, Jest, and Jasmine can be helpful.

3 Functional Programming:

Embrace functional programming principles like immutability and avoiding shared state to create more predictable and robust functions.

4 Consistency:

Maintain a consistent coding style and adhere to coding standards within your project to make the codebase more predictable.

5 Avoid Magic Values:

Replace hard-coded "magic values" with named constants or configuration options to make the code more understandable and maintainable.

6 Use Built-In Methods:

JavaScript provides many built-in methods for common operations (e.g., Array.map(), Array.filter(), Array.reduce()). Utilize these methods when appropriate to improve code readability and reliability.
By following these principles and practices, you can create JavaScript functions that are more reliable, easier to maintain, and less prone to errors. Building robust functions is a key part of writing high-quality JavaScript code.


Ques 3  Car Description Class.

Ans  

Creating a class for a car description is a common task in object-oriented programming. You can define a Car class that contains properties and methods to describe a car's attributes. Here's a basic example of how you can create a Car class in JavaScript:

class Car {
  constructor(make, model, year, color) {
    this.make = make;
    this.model = model;
    this.year = year;
    this.color = color;
    this.isRunning = false;
  }

  start() {
    if (!this.isRunning) {
      this.isRunning = true;
      console.log(`${this.year} ${this.make} ${this.model} is now running.`);
    } else {
      console.log(`${this.year} ${this.make} ${this.model} is already running.`);
    }
  }

  stop() {
    if (this.isRunning) {
      this.isRunning = false;
      console.log(`${this.year} ${this.make} ${this.model} has been stopped.`);
    } else {
      console.log(`${this.year} ${this.make} ${this.model} is already stopped.`);
    }
  }

  describe() {
    console.log(`This is a ${this.year} ${this.color} ${this.make} ${this.model}.`);
  }
}

// Usage
const myCar = new Car('Toyota', 'Camry', 2022, 'blue');
myCar.describe();
myCar.start();
myCar.stop();

In this code:

* We define a Car class with a constructor that initializes properties like make, model, year, color, and isRunning.

* The class has methods like start, stop, and describe to interact with the car object. The start and stop methods change the isRunning property and log messages based on the car's current state.

* The describe method provides information about the car.

* Finally, we create an instance of the Car class, myCar, and use it to describe the car, start the engine, and stop the engine.

This is a basic example of a Car class. Depending on your needs, you can add more properties and methods to capture additional car attributes and functionalities.


Ques 4  Employee Class Challenge.

  Ans  Creating an Employee class is a common exercise in object-oriented programming. An Employee class can represent employees in an organization with properties and methods for managing employee information. Here's an example of how to create an Employee class in JavaScript:


  class Employee {
  constructor(firstName, lastName, jobTitle, department, salary) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.jobTitle = jobTitle;
    this.department = department;
    this.salary = salary;
  }

  getFullName() {
    return `${this.firstName} ${this.lastName}`;
  }

  promote(newJobTitle) {
    this.jobTitle = newJobTitle;
    console.log(`${this.getFullName()} has been promoted to ${newJobTitle}.`);
  }

  raiseSalary(amount) {
    this.salary += amount;
    console.log(`${this.getFullName()}'s salary has been increased by $${amount}. New salary: $${this.salary}`);
  }

  describe() {
    console.log(`${this.getFullName()} works as a ${this.jobTitle} in the ${this.department} department.`);
  }
}

// Usage
const employee1 = new Employee('John', 'Doe', 'Software Engineer', 'Engineering', 80000);
employee1.describe();
employee1.raiseSalary(5000);
employee1.promote('Senior Software Engineer');

In this code:

* We define an Employee class with a constructor that initializes properties like firstName, lastName, jobTitle, department, and salary.

* The class has methods like getFullName, promote, raiseSalary, and describe to interact with the employee object. These methods allow you to get the full name of the employee, promote them to a new job title, give them a salary raise, and describe their position within the organization.

* We create an instance of the Employee class, employee1, and use it to describe the employee, raise their salary, and promote them.

You can customize this Employee class further by adding more properties and methods based on your specific requirements for employee management within your organization.

  
Ques  5  Implementing a Person Class with Default Values

Ans  
You can create a Person class with default values for its properties using JavaScript. Here's an example of how to implement a Person class with default values:

class Person {
  constructor(firstName = "John", lastName = "Doe", age = 30) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }

  getFullName() {
    return `${this.firstName} ${this.lastName}`;
  }

  describe() {
    console.log(`${this.getFullName()} is ${this.age} years old.`);
  }
}

// Usage
const person1 = new Person();
const person2 = new Person("Alice", "Smith", 25);

person1.describe(); // John Doe is 30 years old.
person2.describe(); // Alice Smith is 25 years old.


In this code:

* We define a Person class with a constructor that has default values for firstName, lastName, and age. If no values are provided when creating a Person object, these default values are used.

* The getFullName method returns the full name of the person by combining their first and last names.

* The describe method logs information about the person, including their full name and age.

* We create two instances of the Person class, person1 and person2. person1 uses the default values, while person2 provides specific values during object creation.

This allows you to create Person objects with default values for properties while providing the flexibility to override those defaults when needed.


Ques 6  Using Static Method to Add Two Numbers with Calculator Class

Ans You can create a Calculator class with a static method to add two numbers. Static methods are called on the class itself and don't require an instance of the class. Here's an example of how to implement a Calculator class with a static method for adding two numbers:

class Calculator {
  static add(x, y) {
    return x + y;
  }
}

// Usage
const result = Calculator.add(5, 10);
console.log(`The sum is: ${result}`); // The sum is: 15

In this code:

* We define a Calculator class with a static method add that takes two numbers, x and y, and returns their sum.

* We use the static method by calling it on the class itself (Calculator.add(5, 10)) without creating an instance of the Calculator class.

* The result is then logged to the console.

This approach allows you to create utility classes like a Calculator class to encapsulate related functionality without needing to create instances of the class for every operation.


Ques 7. Password Checker.

Ans A password checker is a common utility used to evaluate the strength of a password based on certain criteria, such as length, character complexity, and the presence of special characters. Here's an example of a password checker function in JavaScript:

function isStrongPassword(password) {
  // Password must be at least 8 characters long
  if (password.length < 8) {
    return false;
  }

  // Password must contain at least one uppercase letter
  if (!/[A-Z]/.test(password)) {
    return false;
  }

  // Password must contain at least one lowercase letter
  if (!/[a-z]/.test(password)) {
    return false;
  }

  // Password must contain at least one digit
  if (!/\d/.test(password)) {
    return false;
  }

  // Password must contain at least one special character
  if (!/[!@#\$%\^&\*\(\)_\+=\-\[\]{};':"\\|,.<>\/?]+/.test(password)) {
    return false;
  }

  // If all criteria are met, the password is considered strong
  return true;
}

// Example usage
const password1 = "P@ssw0rd"; // Strong password
const password2 = "weak123";   // Weak password

console.log(isStrongPassword(password1)); // true
console.log(isStrongPassword(password2)); // false


In this code:

* The isStrongPassword function takes a password string as input.

* It checks several criteria to determine if the password is strong:

* The password must be at least 8 characters long.

 - It must contain at least one uppercase letter (A-Z).
 -It must contain at least one lowercase letter (a-z).
 -It must contain at least one digit (0-9).
 -It must contain at least one special character (e.g., !@#$%^&*()_+-=[]{};':"\|,.<>/?).
 
* If all criteria are met, the function returns true, indicating that the password is strong. Otherwise, it returns false.

* Example usage demonstrates checking two passwords, one strong and one weak.

You can adjust the criteria to match your specific password strength requirements. Additionally, you can incorporate this function into your authentication system to enforce strong password policies.

Ques 8  Adding a Method to a Prototype.

Ans  In JavaScript, you can add a method to an object's prototype to make it available to all instances of that object. This is useful when you want to extend the functionality of built-in objects or custom classes. Here's an example of adding a method to a prototype:

// Define a constructor function (class)
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}

// Add a method to the prototype
Person.prototype.getFullName = function() {
  return this.firstName + ' ' + this.lastName;
};

// Create instances of the Person class
const person1 = new Person('John', 'Doe');
const person2 = new Person('Alice', 'Smith');

// Use the added method on the instances
console.log(person1.getFullName()); // "John Doe"
console.log(person2.getFullName()); // "Alice Smith"

In this example:

* We define a constructor function Person that creates instances of a person with firstName and lastName properties.

* We add a method getFullName to the Person prototype. This method concatenates the firstName and lastName properties to return the full name.

* We create two instances of the Person class, person1 and person2.

* We call the getFullName method on each instance to get their full names.

By adding the method to the prototype, the method is shared among all instances of the Person class, making it more memory-efficient and allowing you to update the method for all instances simultaneously if needed.


Ques 9 Check the presence using closures.

Ans Closures in JavaScript allow you to create functions that "remember" the variables and environment in which they were created, even when they are executed in a different scope. You can use closures to check the presence of a value within an enclosing function. Here's an example:

function createPresenceChecker(presenceArray) {
  return function(valueToCheck) {
    return presenceArray.includes(valueToCheck);
  };
}

const fruits = ["apple", "banana", "cherry", "date"];
const isFruitPresent = createPresenceChecker(fruits);

console.log(isFruitPresent("banana")); // true
console.log(isFruitPresent("grape"));  // false

In this code:

* The createPresenceChecker function takes an array presenceArray as a parameter and returns a closure function.

* The closure function checks if a given valueToCheck is present in the presenceArray by using the includes method.

* We create an array fruits and use the createPresenceChecker function to create a closure isFruitPresent that checks if a given value is present in the fruits array.

* When we call isFruitPresent("banana"), it returns true because "banana" is present in the fruits array. Calling isFruitPresent("grape") returns false because "grape" is not in the array.

Closures are useful for encapsulating and reusing functionality, such as checking for the presence of values within a specific context.

Ques 10 Filter by Category.

Ans 

 Filtering an array of objects by category is a common operation in JavaScript. You can use the filter method to accomplish this. Here's an example:

Suppose you have an array of objects representing items, and each item has a category property:

const items = [
  { name: "Item 1", category: "A" },
  { name: "Item 2", category: "B" },
  { name: "Item 3", category: "A" },
  { name: "Item 4", category: "C" },
  { name: "Item 5", category: "B" },
];

You can use the filter method to filter items by a specific category:

function filterByCategory(array, category) {
  return array.filter(item => item.category === category);
}

const categoryAItems = filterByCategory(items, "A");
console.log("Category A Items:", categoryAItems);

const categoryBItems = filterByCategory(items, "B");
console.log("Category B Items:", categoryBItems);


In this code:

* The filterByCategory function takes an array and a category as input.

* It uses the filter method to create a new array containing only the items that match the specified category.

* We call filterByCategory with different categories to create arrays of items for each category.

The resulting arrays, categoryAItems and categoryBItems, will contain the items that belong to the "A" and "B" categories, respectively.

You can use this approach to filter an array of objects by any specific category or criteria, making it a flexible way to extract the data you need.




