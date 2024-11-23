# Coding Style Guidelines for Contributing 
📏 My coding style guidelines for myself and contributors.

## Table of Contents (ToC)
1. [Standard Style Guidelines _(any language)_](#standard-style-guidelines-any-language)
    - 1.1 [Indentation](#11-indentation)
    - 1.2 [Horizontal code limit](#12-horizontal-code-limit)
    - 1.3 [Naming Variables and Functions & Others:](#13-naming-variables-and-functions)
2. [C Language Specific Guidelines](#c-language-specific-guidelines)
    - 2.1 [Functions styling](#21-functions-styling) 
    - 2.2 [Constants](#22-constants)
3. [JavaScript Specific Guidelines](#javascript-specific-guidelines)
    - 3.1 [Arrow functions usage](#31-arrow-function-usage)
    - 3.2 [Single-statement functions](#32-single-statement-functions)
    - 3.3 [Variable Declaration](#33-variable-declaration)
    - 3.4 [String Delimiters](#34-string-delimiters)
4. [Final Notes](#final-notes)


## Standard Style Guidelines _(Any Language)_
### 1.1 Indentation:
- Use **8 spaced tabs** instead of 4 for consistency and readability.


_correct approach:_
```c
void foo(int n) 
{
        for (int i = 0; i < n; i++) {
                puts("bar"); 
        } 
}
```

```JavaScript
static get_quotient(a, b) {
        Math_Utils.verify_passed_arguments(a, b);
        if (b === 0) {
                throw new Error('Cannot divide by zero');
        }
        return Number((a / b).toFixed(4));
}
```
---

### 1.2 Horizontal code limit:
- The maximum code length must be **100 characters per line.**
- **Exceptions:** Only when breaking the line **really** compromises readability or functionality.
- Tip for `VSCode` Users: Add a vertical ruler for visual feedback:

```JavaScript
// settings.json
"editor.rulers": [100]
```
---
### 1.3 Naming Variables and Functions:
- Always use `snake_case` for variables and functions across all contexts.
```JavaScript
get get_full_name() {
        return `${this.name} Doe`;
}
```

```C
bool is_even(int n);
```

## C Language Specific Guidelines

### 2.1 Functions Styling
- Use **Allman Style** for **global functions**:
```c
int foo(void) 
{
        /* Global Function */
}
```
- Use K&R Style (Kernighan and Ritchie) for local **functions or blocks**:

```c
int get_quotient(int a, int b) {
        if (b == 0) {
                return -1;
        }
        return a / b;
}
```
---
### 2.2 Constants 
- Constants must be written in **uppercase** (e.g. `TAX_RATE`, `MAX_PRODUCTS`).
- Global-scoped constants must be defined at the **top of the file** for better visibility.

_correct approach:_
```c
const float TAX_RATE = 0.2;
const int MAX_PRODUCTS = 100;
```

## JavaScript Specific Guidelines

### 3.1 Arrow Function Usage:
- Use **arrow functions** only for **callbacks**.
- Avoid using arrow functions outside of this context, regardless of their size.

_correct example:_
```JavaScript
array.map((item) => item * 2);
```

_incorrect example:_
```JavaScript
const add = (a, b) => a + b;
```
---
### 3.2 Single-Statement Functions:
- For very short functions (e.g., a single statement), write them on a **single line**.
- Always end the function with a semicolon in these cases `(;)`.

_correct example:_
```JavaScript
function add(a, b) { return a + b; };
```

_incorrect example:_
```JavaScript
function add(a, b) { 
        return a + b; 
} // Avoid breaking into multiple lines unnecessarily.
```

---

### 3.3 Variable Declaration:
- Always use the `const` keyword for variable definitions.
- Only use `let` when you are certain the value will change.

_correct example:_
```JavaScript
// Use const for variables that won't change
const username = 'JaneDoe';
const max_retries = 5;

// Use let when the value might change
let attempts = 0;
while (attempts < max_retries) {
    attempts++;
}
```

_incorrect example:_
```JavaScript
// Using let when const would be more appropriate
let username = 'JaneDoe'; // Use const instead, as username does not change
```

## 3.4 String Delimiters:
- Always prefer using **single quotes** for strings, unless the string contains single quotes, 
in which case, use double quotes.

_correct example:_
```JavaScript
const greeting = 'Hello, world!';
const message = 'Such a nice day!';
```

_incorrect example:_
```JavaScript
// Avoid using double quotes for simple strings
const greeting = "hello, world!"; 
```

## Final Notes:
- Adherence to these guidelines ensures consistency and improves readability for all contributors.
