# flashcards
for the learning javascript tutorial
# documentation from each flashcard sections

# substrings

Substrings 

Last updated January 2023
A substring is a part or a portion of a string. For example, "rain" is a substring of the string "brain" because you can get "rain" by taking the last 4 characters.

When working with strings, you often need to get a few characters of a string rather than all of it. Thus we use the substring method.

Substring signature
A function signature gives you an explanation of the parameters that you need to pass for that method. Let's take a look at the signature of substring:

someString.substring(indexStart, indexEnd)
This means that when you call substring, you can give it 2 parameters, the first one for the indexStart and the second one for indexEnd.

indexStart: the position of the first character you'd like to include
indexEnd: the position of the first character you'd like to ignore
This means an indexEnd of 5, will only include up to the character at position 4.

The combination of these 2 will give you a substring.

Let's take an example with a variable named language with a value JavaScript, and let's get the substring with indexStart of 1 and indexEnd of 4. This will return a string made up of all the characters from positions 1 to 3 because 4 is the first character that is ignored:

Substring example

The result of such substring is "ava".

Here's how you'd write it in JavaScript:


const language = "JavaScript";
language.substring(1, 4); //"ava"
Optional parameters
The indexEnd parameter is optional, which means you can pass the indexStart and it'll assume the indexEnd to be the same as the string length. Here's an example:


language.substring(4); //"Script"
It assumed that the indexEnd is the length of the string (10 in this example).

Legacy note
If you already know a bit of JavaScript, you might have used another method that performs a similar result. You can find the name of the function below, but we do not recommend that you use it because it's deprecated.

Do not use the .substr method as it's deprecated and works differently. Always use the .substring method.

Recap
A substring is a part or a portion of a string.
string.substring(indexStart, indexEnd) is used to return a portion of the string.
indexStart: the position of the first character you'd like to include.
indexEnd: the position of the first character you'd like to ignore.
the indexEnd argument is optional which means you can leave it out.
Not useful
Useful

# Text ellipsis Project I 

This is the first challenge where you can use the BROWSER tab.
You are given the code inside the index.html, index.css, and index.js.

You can now try your code by clicking on the BROWSER tab and interacting with the challenge. For example, in this challenge, you can write text inside the given text box.

The code given in the index.js might be completely new to you, as it's the code that manipulates the DOM. This will be explained in several chapters later in this course.

You may also have noticed that the function given to you is preceded by the export keyword. Make sure to keep this keyword as it allows us to import your code in the index.js file. This will also be explained in a later chapter.

Now, here are the instructions for this challenge:
Complete the function getDescription such that it returns the first 10 characters of the text parameter it receives.  

# code

index.js

import {getDescription} from "./helpers.js";

const input = document.querySelector("#input");
const output = document.querySelector("#output");

input.addEventListener("input", (event) => {
    output.textContent = getDescription(event.currentTarget.value);
});


helpers.js

/**
 * @param {string} text
 */
export function getDescription(text) {
    console.log(text); // write something in the BROWSER and see it in the console

}


index.html

<nav class="navbar">
    <h1 class="nav-brand">Text ellipsis</h1>
</nav>

<main class="container">
    <div>
        <label class="label" for="component-name">Enter text<span class="input-required">*</span></label>
        <input type="text" class="input" placeholder="Enter your text here" id="input" autocomplete="off">
    </div>

    <p id="output"></p>
</main>



index.css

<nav class="navbar">
    <h1 class="nav-brand">Text ellipsis</h1>
</nav>

<main class="container">
    <div>
        <label class="label" for="component-name">Enter text<span class="input-required">*</span></label>
        <input type="text" class="input" placeholder="Enter your text here" id="input" autocomplete="off">
    </div>

    <p id="output"></p>
</main>


# Plus operator 

Last updated January 2023
Good job on finishing your first real-world challenge. We will revisit this text ellipsis project several times in the following chapters so that we improve it.

In JavaScript, the plus operator (+) will behave differently based on the types of values you use it with.

You've already seen that 1 + 3 will return the number 4.

However, you could also use the + to concatenate 2 strings together, which means merging them together into 1 string.

Here's an example:


"Hello" + "World" //"HelloWorld"
will return one string: "HelloWorld". This would be useful if you'd like to concatenate 2 or more strings together. For example:


let prefix = "Mrs.";
let name = "Sam";
let string = prefix + " " + name; // "Mrs. Sam"
It's also possible to do the above with string interpolation, which is covered in the next lesson.

+= operator
Say you have the following code:


let name = "Sam";
name = name + " Blue";
console.log(name); // "Sam Blue"
You can rewrite the name = name + in a shorter way using the += operator:


let name = "Sam";
name += " Blue";
console.log(name); // "Sam Blue"
MDN logoAddition assignment (+=) on MDN


Enjoying the course?
Consider sharing with your friends

Facebook
Twitter
Tumblr
E-Mail
Pinterest
LinkedIn
Reddit
XING
WhatsApp
Hacker News
VK
Telegram
Lesson recap
The + operator is used to add 2 numbers
The + operator is used to concatenate 2 strings
Not useful
Useful

# index.js

/**
 * @param {string} firstNameInitial
 * @param {string} lastNameInitial
 */
function concatInitials(firstNameInitial, lastNameInitial) {

}

// Sample usage - do not modify
console.log(concatInitials("J", "D")); // "JD"
console.log(concatInitials("S", "B")); // "SB"

# template strings

Provide accessibility feedback
Learn JavaScript

Flashcards
Trial
Template strings 

Last updated May 2021
You already know that you can create strings with double quotes or single quotes, but as you already know, these strings do not support interpolation.

Template strings, however, support interpolation and other nifty features.

Your first template string

`This is a template string`
The only difference is that template strings start and end with a backtick ` character.

The backtick is above the tab key on International keyboard layouts. For other keyboards, check out these threads for Windows/Linux & mac and look for your keyboard layout.

Multiline strings
Unlike single quote and double quote strings, template strings can span multiple lines. Here's an example:


let text = `This is a multiline
string that
just works!`
Whereas this would have not been possible with a normal string (single quotes or double quotes).

Interpolation
Template strings support interpolation! This means you could write a variable in your string, and get its value. The syntax is straightforward, you wrap your variable name with a dollar sign and curly braces. Let's take an example where we have a variable language with a value of JavaScript.


let language = "JavaScript";
`I am learning ${language}`; //"I am learning JavaScript";
Remember that string interpolation only works with backticks. If you ever try it and it doesn't work, double-check that you're using backticks rather than single or double-quotes.

Additional examples
How to write a multiline string
How to interpolate in JavaScript
Recap
A template string is a string created with the backtick character: `
Template strings can span multiple lines
Template strings support interpolation with the ${variableName} syntax
Not useful
Useful

2.
Strings I

Help

end?: number, Zero-based index number indicating the end of the substring. The substring includes the characters up to, but not including, the character indicated by end. If end is omitted, the characters from start through the end of the original string are returned., Returns the substring at the specified location within a String object., hint


# Nutrition table I 

It's very common in JavaScript to return a string that represents some HTML code. In fact, we'll be doing this quite often in the DOM Chapters. String interpolation comes in handy here because it supports multi-line strings and interpolation.

Complete the function renderTableRow such that it returns the following HTML:

<tr>
    <td>label here</td>
    <td>value here</td>
</tr>
where label here and value here are replaced with the parameters label and value respectively. Make sure to look at the code in the index.js to see how this function is being used (the DOM code will most likely not be understandable at the point, that's because we haven't explained it yet).

Don't forget to look at the end result in the BROWSER tab!

code

index.js

import {renderTableRow} from "./nutrition.js";

let htmlForCarbs = renderTableRow("Carbs", "17g");
let htmlForProtein = renderTableRow("Protein", "19g");
let htmlForFat = renderTableRow("Fat", "5g");

const tbody = document.querySelector("#nutrition-table tbody");
tbody.insertAdjacentHTML("beforeend", htmlForCarbs);
tbody.insertAdjacentHTML("beforeend", htmlForProtein);
tbody.insertAdjacentHTML("beforeend", htmlForFat);


nutrition.js

/**
 * @param {string} label
 * @param {string} value
 */
export function renderTableRow(label, value) {
    return "<tr>\n\t<td>"+label+"</td>\n\t<td>"+value+"</td>\n</tr>"

}


index.html

<nav class="navbar">
    <h1 class="nav-brand">Nutrition table</h1>
</nav>

<main class="container">
    <table class="table" id="nutrition-table">
        <thead>
            <tr>
                <th>Nutrition</th>
                <th>Value</th>
            </tr>
        </thead>
        <tbody></tbody>
    </table>
</main>


index.css

:root {
  --white: #fff;
  --black: #000;

  /* Primary colors*/
  --primary-1: #2b8379;
  --primary-2: #19a596;
  --primary-3: #7fd1c7;
  --primary-4: #7fd1c7;
  --primary-5: #d0f3ef;

  /* Neutral colors */
  --neutral-1: #2c2c2c;
  --neutral-2: #434343;
  --neutral-3: #94868b;
  --neutral-4: #d9cfd3;
  --neutral-5: #f2ecee;

  /* Accent-blue colors */
  --accent-1: #970e3d;
  --accent-2: #c43464;
  --accent-3: #de7699;
  --accent-4: #e6c3ce;
  --accent-5: #fff2f7;
}

body {
  background-color: var(--neutral-5);
  margin: 0;
}

h1 {
  font-size: 36px;
  font-weight: 600;
}

h2 {
  font-size: 28px;
  font-weight: 500;
}

h3 {
  font-size: 24px;
  font-weight: normal;
}

p {
  line-height: 30px;
  font-size: 18px;
}

a {
  color: var(--primary-2);
  font-weight: bold;
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}

.rounded {
  border-radius: 30px;
}

.container {
  max-width: 900px;
  margin: 0 auto;
  padding: 0 20px;
}


/* FORMS */
.form h2 {
  font-size: 24px;
  font-weight: 400;
}

.form h3 {
  font-size: 20px;
  font-weight: 300;
  margin-bottom: 15px;
}

.form-section {
  border-bottom: var(--neutral-4) solid 1px;
  margin-bottom: 20px;
}

.input-required {
  color: var(--primary-2);
  text-decoration: none;
  font-weight: bold;
  padding: 0 1px;
}

.label {
  display: block;
  font-weight: 500;
}

.input {
  font-size: 16px;
  margin-top: 1em;
  margin-bottom: 1.5em;
  padding: 0.75em 0.5em;
  min-width: 200px;
  border: none;
  border-left: 7px solid var(--neutral-4);
  transition: border-left-color 160ms;
  background-color: white;
  width: 100%;
}

::placeholder {
  color: var(--neutral-3);
}

input:not(.btn):focus {
  outline: none;
  border-left: 7px solid var(--primary-1);
}

/* NAVBAR */
.navbar {
  background-color: white;
  padding: 10px;
  box-shadow: 0px 3px 7px 1px rgba(0, 0, 0, 0.07),
    0px -3px 7px 1px rgba(0, 0, 0, 0.07);
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
}

.nav-brand {
  font-weight: 450;
  text-decoration: none;
  padding-left: 20px;
  margin-top: 15px;
  margin-bottom: 15px;
  color: initial;
}

.table {
  width: 100%;
  border-collapse: collapse;
}

.table thead {
  background-color: var(--primary-1);
  color: white;
  border: 1px solid white;
}

.table th {
  padding: 15px;
}
.table td {
  padding: 10px;
}

.table tbody {
  font-size: 18px;
  border: 1px solid white;
}
.table tbody tr:nth-child(2n) {
  background-color: white;
}

.table tbody tr:nth-child(2n + 1) {
  background-color: var(--neutral-5);
}
