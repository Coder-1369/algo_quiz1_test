# Web Development Midterm Study Pack

## Multiple Choice Questions (MCQs)

1. **What is the correct syntax for referring to an external script called `script.js`?**  
   a) `<script src="script.js">`  
   b) `<script href="script.js">`  
   c) `<script name="script.js">`  
   d) None of the above
   
   **Answer:** a  
   **Explanation:** The correct way to include an external JavaScript file is by using the `src` attribute in the `<script>` tag.

2. **Which of the following is not a JavaScript data type?**  
   a) Undefined  
   b) Boolean  
   c) Character  
   d) Number
   
   **Answer:** c  
   **Explanation:** JavaScript has types like undefined, boolean, and number, but does not have a character type; characters are represented using strings.

3. **What will `console.log(typeof NaN)` output?**  
   a) 'number'  
   b) 'undefined'  
   c) 'NaN'  
   d) 'object'
   
   **Answer:** a  
   **Explanation:** `NaN` is of type number in JavaScript, which stands for "Not a Number" but is still classified as a number data type.

4. **Which company developed JavaScript?**  
   a) Mozilla  
   b) Microsoft  
   c) Netscape  
   d) Sun Microsystems
   
   **Answer:** c  
   **Explanation:** JavaScript was developed by Brendan Eich at Netscape.

5. **What is the output of `console.log(0.1 + 0.2 === 0.3)`?**  
   a) true  
   b) false
   
   **Answer:** b  
   **Explanation:** Due to floating-point precision issues, `0.1 + 0.2` does not exactly equal `0.3`.

6. **Which of the following methods can add items to an array?**  
   a) push()  
   b) pop()  
   c) shift()  
   d) splice()
   
   **Answer:** a and d  
   **Explanation:** The `push()` method adds items to the end of an array, while `splice()` can add items at any position.

7. **What does the `this` keyword refer to in JavaScript?**  
   a) The global object  
   b) The object from which the method was called  
   c) None of the above
   
   **Answer:** b  
   **Explanation:** The value of `this` is determined by how a function is called and usually refers to the object from which the method is invoked.

8. **Which symbol is used for comments in JavaScript?**  
   a) //  
   b) /*  
   c) #  
   d) <!--
   
   **Answer:** a and b  
   **Explanation:** JavaScript uses `//` for single-line comments and `/* */` for multi-line comments.

9. **How can you create a function in JavaScript?**  
   a) function:myFunction()  
   b) function myFunction()  
   c) create myFunction()  
   d) function = myFunction()
   
   **Answer:** b  
   **Explanation:** The correct way to declare a function is using the keyword `function` followed by the function name.

## Short Coding Questions

1. **Write a function to check if a number is even or odd.**  
   ```javascript  
   function isEven(num) {  
       return num % 2 === 0;  
   }  
   ```
   **Example:**  
   `console.log(isEven(4)); // true`

2. **Write a JavaScript function to reverse a string.**  
   ```javascript  
   function reverseString(str) {  
       return str.split('').reverse().join('');  
   }  
   ```
   **Example:**  
   `console.log(reverseString('hello')); // 'olleh'`

3. **Create a function that counts the number of vowels in a string.**  
   ```javascript  
   function countVowels(string) {  
       return (string.match(/[aeiou]/gi) || []).length;  
   }  
   ```
   **Example:**  
   `console.log(countVowels('hello world')); // 3`

## Mock Exam

### Mock Exam Questions
1. Question about JavaScript syntax.
2. Question about data types.
3. Question about scope in functions.
4. Question regarding `this` keyword.
5. More questions as per syllabus...

### Answer Key
- 1. b
- 2. a
- 3. d
- 4. c
- 5. b