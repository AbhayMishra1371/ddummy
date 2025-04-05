Okay, here are the code snippets with all comments removed for a cleaner copy-paste experience during hands-on sessions.

*HELLO WORLD*

javascript
console.log("Hello, Web Development World!");
alert("Welcome to JavaScript!");


*VARIABLES AND DATA TYPES*

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


*ARRAY OPERATIONS*

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


*OBJECTS*

javascript
let student = {
  name: "John Doe",
  age: 20,
  courses: ['Web Dev', 'Design'],
  introduce() {
    return `Hi, I'm ${this.name}`;
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


*FUNCTIONS*

javascript
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Traditional"));

const greetArrow = (name) => `Hello, ${name}!`;
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
  console.log(`Hello, ${name}!`);
}
sayHello("Web Wizards");

const add = (x, y) => x + y;
console.log(add(10, 5));


*CALLBACK FUNCTIONS (Example)*

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


*SELECTING HTML ELEMENTS*

javascript
let elementById = document.getElementById('myElement');
let elementsByClass = document.getElementsByClassName('myClass');
let queryElement = document.querySelector('.myClass');
let allQueryElements = document.querySelectorAll('.myClass');

console.log(elementById);
console.log(elementsByClass);
console.log(queryElement);


*CREATING HTML ELEMENTS*

javascript
let newDiv = document.createElement('div');
newDiv.textContent = 'New Dynamic Content';
newDiv.classList.add('dynamic-class');
console.log(newDiv);


*UPDATING AND REMOVING ELEMENTS*

html
<p id="myParagraph">Original Text</p>


javascript
let element = document.getElementById('myParagraph');

if (element) {
  element.innerHTML = '<strong>Updated Content</strong>';
  element.style.color = 'blue';
  element.style.backgroundColor = 'yellow';
  // element.remove();
} else {
  console.log("Element not found!");
}


*EVENTS (Click/Mouse)*

html
<button id="myButton">Click Me</button>


javascript
let myButton = document.getElementById('myButton');

if (myButton) {
  myButton.addEventListener('click', () => {
    console.log('Element clicked!');
    alert('Button was clicked!');
  });
}

document.addEventListener('click', (event) => {
  console.log('Clicked at coordinates:', event.clientX, event.clientY);
});


*EVENTS (Submit)*

html
<form id="myForm">
  <label>Name: <input type="text" name="username"></label>
  <button type="submit">Submit</button>
</form>


javascript
let form = document.getElementById('myForm');

if (form) {
  form.addEventListener('submit', (event) => {
    event.preventDefault();
    console.log('Form submission prevented. Ready for JS handling.');
    alert('Form submit intercepted by JS!');
  });
}

function validateForm() {
  console.log("Validating form...");
  return true;
}


*EVENTS (Keyboard)*

javascript
document.addEventListener('keydown', (event) => {
  console.log(`Key pressed: ${event.key}`);
  if (event.key === 'Enter') {
    console.log('Enter key pressed!');
  }
});


*FORM HANDLING (Data Extraction)*

html
<form id="myForm">
  <label>Name: <input type="text" name="username" value="TestUser"></label>
  <label>Email: <input type="email" name="email" value="test@example.com"></label>
  <button type="submit">Submit</button>
</form>


javascript
let myForm = document.getElementById('myForm');

if (myForm) {
  myForm.addEventListener('submit', (event) => {
    event.preventDefault();
    const formData = new FormData(myForm);
    const data = Object.fromEntries(formData.entries());
    console.log('Form data extracted:', data);
    if (validateFormData(data)) {
       submitFormData(data);
    }
  });
}

function validateFormData(data) {
  console.log("Validating data:", data);
  return data.username && data.email;
}

function submitFormData(data) {
  console.log("Submitting data:", data);
  alert(`Data submitted (simulated): ${JSON.stringify(data)}`);
}


*CLASS MANIPULATION*

html
<div id="toggleDiv" class="box">Toggle Me</div>
<div id="checkDiv" class="box hidden">Check Me</div>
<div id="multiDiv" class="box old-class">Multi Class</div>


javascript
let toggleElement = document.getElementById('toggleDiv');
let checkElement = document.getElementById('checkDiv');
let multiElement = document.getElementById('multiDiv');

if (toggleElement) {
  toggleElement.addEventListener('click', () => {
    toggleElement.classList.toggle('active');
    console.log("Toggled 'active' class. Classes:", toggleElement.className);
  });
}

if (checkElement) {
  if (checkElement.classList.contains('hidden')) {
    console.log('Check element is hidden');
  }
}

if (multiElement) {
  multiElement.classList.add('new-class', 'another-class');
  console.log("Added classes. Now:", multiElement.className);
  multiElement.classList.remove('old-class');
  console.log("Removed 'old-class'. Now:", multiElement.className);
}
