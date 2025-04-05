# Web Wizard 3.0 - JavaScript & DOM Snippets

## Hello World

```javascript
console.log("Hello, Web Development World!");
alert("Welcome to JavaScript!");
```

## Variables and Data Types

```javascript
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
```

## Array Operations

```javascript
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
```

## Objects

```javascript
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
```

## Functions

```javascript
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
```

## Callback Functions

```javascript
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
```

## Selecting Existing Elements

```javascript
let elementById = document.getElementById('header');
let elementsByClass = document.getElementsByClassName('nav-item');
let queryElement = document.querySelector('.content');
let allQueryElements = document.querySelectorAll('p');

console.log(elementById);
console.log(elementsByClass);
console.log(queryElement);
console.log(allQueryElements);

let allLinks = document.querySelectorAll('a');
console.log(`Found ${allLinks.length} links on this page`);

let firstImage = document.querySelector('img');
console.log(firstImage ? firstImage.src : 'No images found');

let bodyElement = document.body;
console.log(bodyElement);
```

## Creating HTML Elements

```javascript
let newDiv = document.createElement('div');
newDiv.textContent = 'New Dynamic Content';
newDiv.classList.add('dynamic-class');
document.body.appendChild(newDiv);

let newButton = document.createElement('button');
newButton.textContent = 'Click Me';
newButton.style.padding = '10px';
newButton.style.backgroundColor = '#4CAF50';
newButton.style.color = 'white';
document.body.appendChild(newButton);
```

## Updating Existing Elements

```javascript
let paragraphs = document.querySelectorAll('p');
if (paragraphs.length > 0) {
  paragraphs[0].innerHTML = '<strong>Updated Content</strong>';
  paragraphs[0].style.color = 'blue';
  paragraphs[0].style.backgroundColor = 'yellow';
}

let headings = document.querySelectorAll('h1, h2, h3');
if (headings.length > 0) {
  headings[0].textContent = 'Modified Heading';
  headings[0].style.fontFamily = 'Arial, sans-serif';
}

let firstDiv = document.querySelector('div');
if (firstDiv) {
  firstDiv.innerText = 'Content changed via console';
  firstDiv.style.border = '2px solid red';
  firstDiv.style.padding = '10px';
}
```

## Working with Events

```javascript
let anyButton = document.querySelector('button');
if (anyButton) {
  anyButton.addEventListener('click', () => {
    console.log('Button clicked!');
    alert('Button was clicked!');
  });
}

document.addEventListener('click', (event) => {
  console.log('Clicked at coordinates:', event.clientX, event.clientY);
});

document.addEventListener('keydown', (event) => {
  console.log(`Key pressed: ${event.key}`);
  if (event.key === 'Enter') {
    console.log('Enter key pressed!');
  }
});

let anyLink = document.querySelector('a');
if (anyLink) {
  anyLink.addEventListener('click', (event) => {
    event.preventDefault();
    console.log('Link click prevented');
    console.log('Would have gone to:', anyLink.href);
  });
}
```

## Form Interaction

```javascript
let anyForm = document.querySelector('form');
if (anyForm) {
  anyForm.addEventListener('submit', (event) => {
    event.preventDefault();
    console.log('Form submission prevented');
    
    const formData = new FormData(anyForm);
    const data = Object.fromEntries(formData.entries());
    console.log('Form data:', data);
  });
}

let inputFields = document.querySelectorAll('input');
console.log(`Found ${inputFields.length} input fields`);

if (inputFields.length > 0) {
  inputFields[0].value = 'Changed via console';
  
  inputFields[0].addEventListener('input', (event) => {
    console.log('Input changed to:', event.target.value);
  });
}
```

## Class Manipulation

```javascript
let targetElement = document.querySelector('.some-class');
if (targetElement) {
  targetElement.classList.add('highlight');
  console.log('Current classes:', targetElement.className);
  
  targetElement.classList.toggle('visible');
  console.log('After toggle:', targetElement.className);
  
  targetElement.classList.remove('some-class');
  console.log('After removal:', targetElement.className);
  
  console.log('Has highlight class?', targetElement.classList.contains('highlight'));
}

let allParagraphs = document.querySelectorAll('p');
allParagraphs.forEach((p, index) => {
  p.classList.add('modified-element');
  if (index % 2 === 0) {
    p.classList.add('even-element');
  }
});
```

## DOM Traversal

```javascript
let startElement = document.querySelector('ul');
if (startElement) {
  let parent = startElement.parentElement;
  console.log('Parent element:', parent);
  
  let children = startElement.children;
  console.log('Child elements:', children);
  console.log(`Number of children: ${children.length}`);
  
  let firstChild = startElement.firstElementChild;
  console.log('First child:', firstChild);
  
  let nextSibling = startElement.nextElementSibling;
  console.log('Next sibling:', nextSibling);
}

let deepElement = document.querySelector('.nested-content');
if (deepElement) {
  console.log('Closest ul:', deepElement.closest('ul'));
  console.log('All parents with class:', deepElement.closest('.container'));
}
```

## Style Manipulation

```javascript
let styleTarget = document.querySelector('div');
if (styleTarget) {
  styleTarget.style.backgroundColor = '#f0f0f0';
  styleTarget.style.color = '#333';
  styleTarget.style.padding = '20px';
  styleTarget.style.borderRadius = '5px';
  styleTarget.style.boxShadow = '0 4px 8px rgba(0,0,0,0.2)';
  styleTarget.style.transition = 'all 0.3s ease';
  
  setTimeout(() => {
    styleTarget.style.backgroundColor = '#ffeb3b';
    styleTarget.style.transform = 'scale(1.05)';
  }, 2000);
}

let pageBody = document.body;
pageBody.style.fontFamily = 'Arial, sans-serif';
```

## Useful Console Techniques

```javascript
console.log('Basic logging');
console.error('Error message');
console.warn('Warning message');

console.group('Grouped Messages');
console.log('Detail 1');
console.log('Detail 2');
console.groupEnd();

console.time('Timer');
setTimeout(() => {
  console.timeEnd('Timer');
}, 1000);

let debugObject = { a: 1, b: { c: 3, d: [4, 5, 6] } };
console.log('Simple output:', debugObject);
console.dir(debugObject);

console.table([
  { name: 'John', age: 25, role: 'Developer' },
  { name: 'Jane', age: 30, role: 'Designer' },
  { name: 'Bob', age: 22, role: 'Intern' }
]);
```
