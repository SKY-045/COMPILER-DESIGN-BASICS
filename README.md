# COMPILER-DESIGN-BASICS

COMPANY: CODTECH IT SOLUTION

NAME: SAURABH KUMAR

INTERN ID: CT04DF95

DOMAIN: C++

DURATION: 4 WEEKS

MENTOR: NEELA SANTOSH

# DESCRIPTION

Mini Arithmetic Expression Compiler in C++ — Description
This program is a compact and efficient arithmetic expression parser and evaluator written in C++. It functions as a mini compiler for mathematical expressions entered by the user, supporting basic arithmetic operations: addition (+), subtraction (-), multiplication (*), division (/), and parentheses for grouping (()).

The program reads an expression from the user as a string and parses it using a recursive descent parser, evaluating the result in real time. This approach mirrors the way many real-world interpreters and compilers parse mathematical or logical expressions.

Core Components
1. Class: Parser
The entire parsing and evaluation logic is encapsulated in the Parser class. This class has two private members:

input: The arithmetic expression string.

pos: The current parsing position in the string.

Several helper functions are defined to manage parsing, whitespace skipping, and recursive evaluation.

2. Recursive Descent Parsing
The parsing logic is implemented using recursive descent, a top-down approach where each grammar rule is handled by a separate function.

Parsing Grammar Overview
The grammar used by the parser is:

ini
Copy
Edit
expression = term { ('+' | '-') term }
term       = factor { ('*' | '/') factor }
factor     = number | '(' expression ')'
Each non-terminal in the grammar corresponds to a parsing function:

parseExpression(): Handles addition and subtraction.

parseTerm(): Handles multiplication and division.

parseFactor(): Handles numbers and parenthesized expressions.

This order ensures correct operator precedence, where multiplication and division are evaluated before addition and subtraction, and parentheses override the default precedence.

3. Detailed Function Breakdown
peek() and get()
peek() looks at the current character without consuming it.

get() returns the current character and advances the parsing position.

These help implement a lookahead parser without using external tools.

skipWhitespace()
This function skips any whitespace characters so that expressions like 3 + 4 * ( 2 -1 ) are parsed correctly.

parseFactor()
Handles the lowest level of the grammar:

If the next character is (, it parses the expression inside the parentheses recursively.

Otherwise, it reads a number character by character (including decimal points) and converts it to a double using stod.

parseTerm() and parseExpression()
These functions apply the operators in the correct order:

parseTerm() repeatedly evaluates and combines factors using * or /.

parseExpression() then evaluates and combines those terms using + or -.

Each function uses a while loop to handle multiple consecutive operations, such as 3 + 4 - 2 + 1.

4. Evaluation Flow
In the main() function:

The user is prompted to enter an arithmetic expression.

The expression is passed to the evaluate() method of the Parser class.

The parser computes the result recursively and returns it.

If an error occurs during parsing (e.g., unexpected characters or missing parentheses), an exception is thrown and caught in the try-catch block, displaying an error message.

Features and Strengths
Supports Nested Parentheses: Correctly evaluates expressions like 2 * (3 + (4 - 1)).

Floating-Point Support: Accepts and calculates with decimal numbers (e.g., 3.14 * 2).

Operator Precedence: Implements standard arithmetic precedence without explicit parsing tables.

Minimal Dependencies: Uses only standard C++ headers (<iostream>, <string>, <stdexcept>).

Robust Error Handling: Uses exceptions to signal syntax errors like missing parentheses or malformed numbers.

Limitations and Extensions
Current limitations:

No support for unary minus (e.g., -3 + 2 will not work).

No variables or assignment.

No exponentiation (^ operator).

Potential extensions:

Add unary operators and exponentiation.

Support variables and assignment.

Implement functions like sin(), cos(), etc.

Conclusion
This mini arithmetic expression compiler in C++ is a powerful demonstration of recursive descent parsing, one of the most fundamental techniques in compiler construction. Despite its simplicity, the program handles complex mathematical expressions with correct precedence and associativity. It's an excellent educational tool for understanding parsing, compiler design principles, and expression evaluation in programming languages.

# output
![Image](https://github.com/user-attachments/assets/928f9c0a-02cd-4c16-b24c-6c607927d0a6)
