Okay, here is the collection of JavaScript and related HTML snippets formatted correctly for a Markdown (README.md) file. This uses H2 headings for topics and fenced code blocks with language identifiers for syntax highlighting and easy copying.

markdown
# Web Wizard 3.0 - JavaScript & DOM Snippets

This file contains JavaScript code snippets from the Web Wizard 3.0 presentation, intended for easy reference and copy-pasting during hands-on sessions.

## Hello World

javascript
console.log("Hello, Web Development World!");
alert("Welcome to JavaScript!");


## Variables and Data Types

javascript
let dynamicVariable = "I can change";
const constantVariable = "I stay the same";
var oldSchoolVariable = "Legacy declaration";

let stringExample = "Hello, JavaScript";
let numberExample = 42;
let booleanExample = true;
let undefinedExample = undefined;
let nullExample = null;

let message = "Web Wizard";
console.log(message);
message = "JS is fun!";
console.log(message);

const year = 2024;
console.log(year);


## Array Operations

javascript
let fruits = ['Apple', 'Banana', 'Cherry'];

console.log(fruits[0]);

fruits.push('Date');
fruits.unshift('Grape');
console.log(fruits);

let lastFruit = fruits.pop();
let firstFruit = fruits.shift();
console.log(fruits);

let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(num => num * 2);
let evenNumbers = numbers.filter(num => num % 2 === 0);
let sum = numbers.reduce((acc, curr) => acc + curr, 0);

console.log(doubled);
console.log(evenNumbers);
console.log(sum);

let colors = ['red', 'green'];
colors.push('blue');
console.log(colors);
console.log(colors[0]);


## Objects

javascript
let student = {
  name: "John Doe",
  age: 20,
  courses: ['Web Dev', 'Design'],
  introduce() {
    return Hi, I'm ${this.name};
  }
};

console.log(student.name);
console.log(student['age']);
console.log(student.introduce());

student.grade = 'A';
student.courses.push('Marketing');
console.log(student);

const { name, age } = student;
console.log(name);
console.log(age);

let car = { make: "Toyota", model: "Camry", year: 2021 };
console.log(car.model);
car.color = "Silver";
console.log(car);


## Functions

javascript
function greet(name) {
  return Hello, ${name}!;
}
console.log(greet("Traditional"));

const greetArrow = (name) => Hello, ${name}!;
console.log(greetArrow("Arrow"));

const calculate = (a, b, operation) => {
  switch(operation) {
    case 'add': return a + b;
    case 'subtract': return a - b;
    default: return 0;
  }
};
console.log(calculate(10, 5, 'add'));
console.log(calculate(10, 5, 'subtract'));

[1, 2, 3].forEach(number => {
  console.log(number * 2);
});

function sayHello(name) {
  console.log(Hello, ${name}!);
}
sayHello("Web Wizards");

const add = (x, y) => x + y;
console.log(add(10, 5));


## Callback Functions (Example)

javascript
function mainFunctionConceptual(param, callbackFunction) {
  console.log('Main function executed');
  callbackFunction();
}

function mainFunctionActual(x, callback) {
  let result = x * 2;
  callback(result);
}

mainFunctionActual(5, function(value) {
  console.log('Callback result:', value);
});


## Selecting HTML Elements

### Example HTML
html
<div id="myElement">Element with ID</div>
<p class="myClass">First Paragraph with Class</p>
<p class="myClass">Second Paragraph with Class</p>


### JavaScript
javascript
let elementById = document.getElementById('myElement');
let elementsByClass = document.getElementsByClassName('myClass');
let queryElement = document.querySelector('.myClass');
let allQueryElements = document.querySelectorAll('.myClass');

console.log(elementById);
console.log(elementsByClass);
console.log(queryElement); // Selects the first paragraph only
console.log(allQueryElements); // Selects both paragraphs


## Creating HTML Elements

javascript
let newDiv = document.createElement('div');
newDiv.textContent = 'New Dynamic Content';
newDiv.classList.add('dynamic-class');
console.log(newDiv);

// Note: To make this element visible on the page,
// you need to append it to an existing element, e.g.:
// document.body.appendChild(newDiv);


## Updating and Removing Elements

### Example HTML
html
<p id="myParagraph">Original Text</p>


### JavaScript
javascript
let element = document.getElementById('myParagraph');

if (element) {
  element.innerHTML = '<strong>Updated Content</strong>';
  element.style.color = 'blue';
  element.style.backgroundColor = 'yellow';

  // Uncomment the next line to remove the element
  // element.remove();
} else {
  console.log("Element 'myParagraph' not found!");
}


## Events (Click/Mouse)

### Example HTML
html
<button id="myButton">Click Me</button>


### JavaScript
javascript
let myButton = document.getElementById('myButton');

if (myButton) {
  myButton.addEventListener('click', () => {
    console.log('Element clicked!');
    alert('Button was clicked!');
  });
}

document.addEventListener('click', (event) => {
  // Logs coordinates relative to the viewport
  console.log('Clicked at coordinates:', event.clientX, event.clientY);
});


## Events (Submit)

### Example HTML
html
<form id="myForm">
  <label>Name: <input type="text" name="username"></label>
  <button type="submit">Submit</button>
</form>


### JavaScript
javascript
let form = document.getElementById('myForm');

if (form) {
  form.addEventListener('submit', (event) => {
    event.preventDefault(); // IMPORTANT: Stops page reload
    console.log('Form submission prevented. Ready for JS handling.');
    alert('Form submit intercepted by JS!');
    // validateForm(); // Example call to a validation function
  });
}

// Dummy function for the example
function validateForm() {
  console.log("Validating form...");
  return true;
}


## Events (Keyboard)

javascript
document.addEventListener('keydown', (event) => {
  console.log(Key pressed: ${event.key});
  if (event.key === 'Enter') {
    console.log('Enter key pressed!');
    // alert('Enter was pressed!'); // Optional alert
  }
});


## Form Handling (Data Extraction)

### Example HTML
html
<form id="dataForm">
  <label>Name: <input type="text" name="username" value="TestUser"></label>
  <label>Email: <input type="email" name="email" value="test@example.com"></label>
  <button type="submit">Submit Data</button>
</form>


### JavaScript
javascript
let dataForm = document.getElementById('dataForm');

if (dataForm) {
  dataForm.addEventListener('submit', (event) => {
    event.preventDefault();
    const formData = new FormData(dataForm);
    const data = Object.fromEntries(formData.entries());

    console.log('Form data extracted:', data);

    if (validateFormData(data)) {
       submitFormData(data);
    }
  });
}

// Dummy validation function
function validateFormData(data) {
  console.log("Validating data:", data);
  // Replace with real validation logic
  return data.username && data.email;
}

// Dummy submission function
function submitFormData(data) {
  console.log("Submitting data:", data);
  // Replace with logic to send data (e.g., using fetch API)
  alert(Data submitted (simulated): ${JSON.stringify(data)});
}


## Class Manipulation

### Example HTML
html
<div id="toggleDiv" class="box">Toggle Me</div>
<div id="checkDiv" class="box hidden">Check Me</div>
<div id="multiDiv" class="box old-class">Multi Class</div>
<style>
  .box { padding: 10px; border: 1px solid #ccc; margin: 5px; }
  .active { background-color: lightblue; font-weight: bold; }
  .hidden { display: none; }
  .new-class { border-color: green; }
  .another-class { color: purple; }
</style>


### JavaScript
javascript
let toggleElement = document.getElementById('toggleDiv');
let checkElement = document.getElementById('checkDiv');
let multiElement = document.getElementById('multiDiv');

if (toggleElement) {
  toggleElement.addEventListener('click', () => {
    toggleElement.classList.toggle('active');
    console.log("Toggled 'active' class. Current classes:", toggleElement.className);
  });
}

if (checkElement) {
  if (checkElement.classList.contains('hidden')) {
    console.log('Check element initially contains "hidden" class.');
    // Example: remove hidden after 2 seconds
    // setTimeout(() => { checkElement.classList.remove('hidden'); }, 2000);
  }
}

if (multiElement) {
  multiElement.classList.add('new-class', 'another-class');
  console.log("Added classes. Current classes:", multiElement.className);
  multiElement.classList.remove('old-class');
  console.log("Removed 'old-class'. Current classes:", multiElement.className);
}
```
```
