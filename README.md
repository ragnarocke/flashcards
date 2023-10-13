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





