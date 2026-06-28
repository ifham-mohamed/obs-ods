
2025-02-17 18:14

Status:

Tags:

#### Topics to Cover:
- **Syntax and Data Types**: Variables, constants, data types, operators.
- **Control Structures**: If-else, loops (for, while, do-while), switch-case.
- **Functions and Methods**: Defining methods, parameters, return types.
- **Object-Oriented Programming (OOP)**: Classes, objects, inheritance, polymorphism, encapsulation, abstraction.
- **Exception Handling**: Try-catch-finally blocks, custom exceptions.
- **Collections**: Lists, dictionaries, arrays, queues, stacks.
- **LINQ (Language Integrated Query)**: Querying collections and databases using LINQ.
- **Delegates and Events**: Understanding delegates, lambda expressions, and events.
- **Asynchronous Programming**: Async/await, Task Parallel Library (TPL).

# Technical - Understand the Basics of C Sharp

## 1. Understanding `Console.Write` vs `Console.WriteLine` in C#

#### **What is a Programming Language?**
A programming language like **C#** allows you to write instructions (code) that the computer can execute. These instructions are written in **human-readable syntax** and then **compiled** into machine code for the computer's CPU to understand.

---

#### **How Does Compilation Work?**
When you run your C# program:
1. The **compiler** converts your code into a format the computer understands.
2. The compiled code is executed line by line.

For example, when you click "Run," this happens:
```csharp
Console.WriteLine("Hello World!");
```
- The compiler translates it into machine code.
- The output is displayed:  
  **Output:**  
  ```
  Hello World!
  ```

---

#### **Key Concepts: Classes, Methods, and Syntax**
- **Class**: A container for related methods. Example: `Console`.
- **Method**: A block of code that performs a specific task. Example: `WriteLine()`.
- **Syntax**: Rules for writing code. For example:
  - Use **parentheses** `()` to call methods.
  - End statements with a **semicolon** `;`.

---

#### **Difference Between `Console.Write` and `Console.WriteLine`**
Both print text, but they handle newlines differently:

1. **`Console.Write`**:
   - Prints text **without adding a newline**.
   ```csharp
   Console.Write("Hello ");
   Console.Write("World!");
   ```
   **Output:**  
   ```
   Hello World!
   ```

2. **`Console.WriteLine`**:
   - Prints text **and adds a newline** at the end.
   ```csharp
   Console.WriteLine("Hello");
   Console.WriteLine("World!");
   ```
   **Output:**  
   ```
   Hello
   World!
   ```

---

#### **Flow of Execution**
Code runs **line by line**:
- If you use `Console.Write`, the next output stays on the same line.
- If you use `Console.WriteLine`, the next output moves to a new line.

---

#### **Summary**
- Use **`Console.Write`** when you want text to stay on the same line.
- Use **`Console.WriteLine`** when you want text to move to a new line after printing.

**Quick Cheat Sheet:**
```csharp
Console.Write("Stay on same line. "); // No newline
Console.WriteLine("Move to next line!"); // Adds newline
```

**Output:**
```
Stay on same line. Move to next line!
```


---

![[Pasted image 20250217205528.png | 700]]


    
### **Explanation of the Diagram**

1. **Human-Written C# Code**:  
   - This is the source code written by developers in C# using human-readable syntax.

2. **Compiler**:  
   - The **C# Compiler** (e.g., `csc.exe`) converts the human-written C# code into **Intermediate Language (IL)** code.  
   - IL is a low-level, platform-independent representation of your code.

3. **Intermediate Language (IL) Code**:  
   - IL is stored in assemblies (`.dll` or `.exe` files).  
   - It is not directly executable by the CPU but serves as an intermediate step.

4. **Common Language Runtime (CLR)**:  
   - The CLR is part of the .NET runtime environment.  
   - It manages the execution of IL code and provides services like garbage collection, exception handling, and security.

5. **Just-In-Time (JIT) Compiler**:  
   - The CLR uses the JIT compiler to convert IL code into **native machine code** at runtime.  
   - This ensures the code is optimized for the specific hardware it runs on.

6. **Machine Code**:  
   - The final output of the JIT compiler is **machine code**, which consists of binary instructions that the CPU can execute directly.

7. **CPU Execution**:  
   - The CPU executes the machine code, performing the operations defined in the original C# program.

---

![[Pasted image 20250217205624.png]]


## 2. Syntax and Data Types - ( Variables, constants, data types, operators)

### **Printing Literal Values in C#**

#### **What is a Literal Value?**
A literal value is a constant value that doesn't change. Examples include strings, characters, integers, floating-point numbers, and Booleans.

---

### **1. String Literals**
Use double quotes (`"`) for strings.

**Correct Code:**
```csharp
Console.WriteLine("Hello World!");
```
**Output:**
```
Hello World!
```

**Wrong Code:**
```csharp
Console.WriteLine('Hello World!');
```
**Error:**
```
error CS1012: Too many characters in character literal
```

---

### **2. Character Literals**
Use single quotes (`'`) for a single character.

**Correct Code:**
```csharp
Console.WriteLine('b');
```
**Output:**
```
b
```

**Wrong Code:**
```csharp
Console.WriteLine('Hello');
```
**Error:**
```
error CS1012: Too many characters in character literal
```

---

### **3. Integer Literals**
No quotes or suffixes are needed for whole numbers.

**Correct Code:**
```csharp
Console.WriteLine(123);
```
**Output:**
```
123
```

---

### **4. Floating-Point Literals**
Use `F` for `float`, no suffix for `double`, and `M` for `decimal`.

**Float Example:**
```csharp
Console.WriteLine(0.25F);
```
**Output:**
```
0.25
```

**Double Example:**
```csharp
Console.WriteLine(2.625);
```
**Output:**
```
2.625
```

**Decimal Example:**
```csharp
Console.WriteLine(12.39816m);
```
**Output:**
```
12.39816
```

---

### **5. Boolean Literals**
Use `true` or `false` without quotes.

**Correct Code:**
```csharp
Console.WriteLine(true);
Console.WriteLine(false);
```
**Output:**
```
True
False
```

**Wrong Code:**
```csharp
Console.WriteLine("true");
```
**Output:**
```
true
```
(Note: This prints the string `"true"`, not the Boolean value.)

---

### **Why Data Types Matter**
Data types define what you can do with values:
- Use `string` for text (e.g., `"Hello"`).
- Use `char` for single characters (e.g., `'A'`).
- Use `int` for whole numbers (e.g., `123`).
- Use `float`, `double`, or `decimal` for numbers with decimals.
- Use `bool` for true/false logic.

**Key Takeaway:**
Even if outputs look similar, their underlying data types determine their behavior. For example:
```csharp
Console.WriteLine("123"); // String
Console.WriteLine(123);   // Integer
```


### **Understanding Variables in C#**

#### **What is a Variable?**
A variable is a container to store data that can change during program execution. You declare a variable by specifying its **data type** and giving it a **name**.

---

### **Declaring and Using Variables**
1. **Declare a Variable:**
   ```csharp
   string firstName;
   ```
   - Declares a variable `firstName` of type `string`.

2. **Assign a Value (Set):**
   ```csharp
   firstName = "Bob";
   ```
   - Assigns the value `"Bob"` to `firstName`.

3. **Retrieve a Value (Get):**
   ```csharp
   Console.WriteLine(firstName);
   ```
   - Retrieves and prints the value of `firstName`.  
   **Output:**
   ```
   Bob
   ```

---

### **Common Mistakes and Errors**
1. **Improper Assignment Order:**
   ```csharp
   "Bob" = firstName;
   ```
   **Error:**
   ```
   error CS0131: The left-hand side of an assignment must be a variable, property or indexer
   ```

2. **Assigning Wrong Data Type:**
   ```csharp
   int firstName;
   firstName = "Bob";
   ```
   **Error:**
   ```
   error CS0029: Cannot implicitly convert type 'string' to 'int'
   ```

3. **Using Uninitialized Variables:**
   ```csharp
   string firstName;
   Console.WriteLine(firstName);
   ```
   **Error:**
   ```
   error CS0165: Use of unassigned local variable 'firstName'
   ```

---

### **Reassigning and Initializing Variables**

1. **Reassign Values:**
   ```csharp
   string firstName = "Bob";
   Console.WriteLine(firstName); // Output: Bob
   firstName = "Liem";
   Console.WriteLine(firstName); // Output: Liem
   firstName = "Isabella";
   Console.WriteLine(firstName); // Output: Isabella
   firstName = "Yasmin";
   Console.WriteLine(firstName); // Output: Yasmin
   ```

2. **Initialize at Declaration:**
   ```csharp
   string firstName = "Bob";
   Console.WriteLine(firstName); // Output: Bob
   ```

---

### **Key Takeaways**
- **Declare:** Specify the data type and name.
- **Set:** Assign a value using `=.
- **Get:** Retrieve the value by using the variable name.

- **Rules:**
  - Assignment happens **right-to-left**.
  - Variables must be initialized before use.
  - Follow naming conventions (e.g., camelCase).

---

### **Quick Cheat Sheet**
```csharp
// Declare and initialize
string name = "Alice";

// Reassign
name = "Bob";

// Print
Console.WriteLine(name); // Output: Bob

// Common Errors
// Error: Wrong order
// "Bob" = name; // CS0131
// Error: Wrong type
// int age = "Twenty"; // CS0029
// Error: Uninitialized
// string city; Console.WriteLine(city); // CS0165
```


concise summary of the **common data types** in C# along with examples:

---

### **1. `string`**
- **Purpose:** Used for text or alphanumeric data.
- **Example:**
  ```csharp
  string greeting = "Hello, World!";
  Console.WriteLine(greeting); // Output: Hello, World!
  ```

---

### **2. `char`**
- **Purpose:** Used for single characters.
- **Example:**
  ```csharp
  char letter = 'A';
  Console.WriteLine(letter); // Output: A
  ```

---

### **3. `int`**
- **Purpose:** Used for whole numbers (no decimals).
- **Range:** -2,147,483,648 to 2,147,483,647.
- **Example:**
  ```csharp
  int age = 25;
  Console.WriteLine(age); // Output: 25
  ```

---

### **4. `float`**
- **Purpose:** Used for floating-point numbers with ~6-9 digits of precision.
- **Suffix:** Append `F` or `f`.
- **Example:**
  ```csharp
  float temperature = 98.6F;
  Console.WriteLine(temperature); // Output: 98.6
  ```

---

### **5. `double`**
- **Purpose:** Used for floating-point numbers with ~15-17 digits of precision.
- **Default:** Decimal numbers are treated as `double` unless specified otherwise.
- **Example:**
  ```csharp
  double pi = 3.14159;
  Console.WriteLine(pi); // Output: 3.14159
  ```

---

### **6. `decimal`**
- **Purpose:** Used for high-precision decimal numbers (e.g., financial calculations).
- **Suffix:** Append `M` or `m`.
- **Example:**
  ```csharp
  decimal price = 19.99m;
  Console.WriteLine(price); // Output: 19.99
  ```

---

### **7. `bool`**
- **Purpose:** Used for true/false logic.
- **Values:** `true` or `false`.
- **Example:**
  ```csharp
  bool isRaining = true;
  Console.WriteLine(isRaining); // Output: True
  ```

---

### **8. `long`**
- **Purpose:** Used for large whole numbers.
- **Range:** -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.
- **Example:**
  ```csharp
  long population = 7800000000;
  Console.WriteLine(population); // Output: 7800000000
  ```

---

### **9. `byte`**
- **Purpose:** Used for small whole numbers (0 to 255).
- **Example:**
  ```csharp
  byte smallNumber = 255;
  Console.WriteLine(smallNumber); // Output: 255
  ```

---

### **10. `short`**
- **Purpose:** Used for small whole numbers.
- **Range:** -32,768 to 32,767.
- **Example:**
  ```csharp
  short smallValue = 32000;
  Console.WriteLine(smallValue); // Output: 32000
  ```

---

### **11. `DateTime`**
- **Purpose:** Used for dates and times.
- **Example:**
  ```csharp
  DateTime today = DateTime.Now;
  Console.WriteLine(today); // Output: Current date and time (e.g., 10/15/2023 3:45:00 PM)
  ```

---

### **12. `var` (Implicitly Typed Variables)**
- **Purpose:** The compiler infers the type based on the assigned value.
- **Example:**
  ```csharp
  var number = 42; // Compiler infers 'int'
  var name = "Alice"; // Compiler infers 'string'
  Console.WriteLine(number); // Output: 42
  Console.WriteLine(name);   // Output: Alice
  ```

---

### **Summary Table**

| **Data Type** | **Purpose**                            | **Example**    |
| ------------- | -------------------------------------- | -------------- |
| `string`      | Text                                   | `"Hello"`      |
| `char`        | Single character                       | `'A'`          |
| `int`         | Whole numbers                          | `42`           |
| `float`       | Small decimal numbers (~6-9 digits)    | `3.14F`        |
| `double`      | Larger decimal numbers (~15-17 digits) | `3.14159`      |
| `decimal`     | High-precision decimal numbers         | `19.99m`       |
| `bool`        | True/False logic                       | `true`         |
| `long`        | Large whole numbers                    | `7800000000`   |
| `byte`        | Small whole numbers (0–255)            | `255`          |
| `short`       | Smaller whole numbers                  | `32000`        |
| `DateTime`    | Dates and times                        | `DateTime.Now` |
| `var`         | Implicitly typed variables             | `var x = 10;`  |

---

### Variable Naming Rules and Conventions with Examples

Here’s a breakdown of the rules and conventions for naming variables in C#, along with examples to illustrate each point:

---

### **1. Variable Names Can Contain Alphanumeric Characters and Underscores**
- **Allowed Characters:** Letters (`a-z`, `A-Z`), digits (`0-9`), and underscores (`_`).
- **Not Allowed:** Special characters like `#`, `$`, `@`, etc.

**Examples:**
```csharp
int studentCount;      // Valid
string fullName;       // Valid
double _temperature;   // Valid (starts with an underscore)
```

**Invalid Examples:**
```csharp
int student#Count;     // Invalid (contains '#')
string full-name;      // Invalid (contains '-')
double 123value;       // Invalid (starts with a number)
```

---

### **2. Variable Names Must Begin with a Letter or Underscore**
- **First Character:** Must be a letter (`a-z`, `A-Z`) or an underscore (`_`).
- **Cannot Start with a Number.**

**Examples:**
```csharp
int age;               // Valid
string _address;       // Valid
double temperature;    // Valid
```

**Invalid Examples:**
```csharp
int 123student;        // Invalid (starts with a number)
string @email;         // Invalid (special character '@')
```

---

### **3. Variable Names Are Case-Sensitive**
- **Case Matters:** `value` and `Value` are treated as two different variables.

**Examples:**
```csharp
int value = 10;
int Value = 20;

Console.WriteLine(value); // Output: 10
Console.WriteLine(Value); // Output: 20
```

---

### **4. Variable Names Must Not Be C# Keywords**
- **Reserved Words:** Cannot use keywords like `int`, `string`, `decimal`, etc., as variable names.

**Examples:**
```csharp
int number;            // Valid
string name;           // Valid
```

**Invalid Examples:**
```csharp
int int;               // Invalid (keyword 'int' used as variable name)
string string;         // Invalid (keyword 'string' used as variable name)
```

---

### **5. Use Camel Case**
- **Camel Case:** First word starts with a lowercase letter, subsequent words start with uppercase letters.
- **Example Format:** `thisIsCamelCase`.

**Examples:**
```csharp
int studentCount;          // Valid (camelCase)
string firstName;          // Valid (camelCase)
double totalAmount;        // Valid (camelCase)
```

**Invalid Examples:**
```csharp
int StudentCount;          // Invalid (PascalCase, not camelCase)
string firstname;          // Invalid (no capitalization for second word)
double TOTALAMOUNT;        // Invalid (all uppercase)
```

---

### **6. Avoid Using Underscores for General Variables**
- **Underscores:** Typically reserved for special cases (e.g., private fields in classes).

**Examples:**
```csharp
int score;                // Valid (no underscore)
string userName;          // Valid (no underscore)
```

**Special Case Example:**
```csharp
private string _userName; // Valid (underscore used for private field)
```

---

### **7. Be Descriptive and Meaningful**
- **Descriptive Names:** Choose names that clearly describe the purpose of the variable.

**Examples:**
```csharp
int numberOfStudents;     // Descriptive
string customerName;      // Descriptive
double totalPrice;        // Descriptive
```

**Invalid Examples:**
```csharp
int x;                    // Too vague
string data;              // Not descriptive
double val;               // Unclear purpose
```

---

### **8. Avoid Contractions or Abbreviations**
- **Full Words:** Use complete words instead of abbreviations or contractions.

**Examples:**
```csharp
int studentCount;         // Clear and complete
string customerAddress;   // Clear and complete
```

**Invalid Examples:**
```csharp
int studCnt;              // Abbreviation (unclear)
string custAddr;          // Abbreviation (unclear)
```

---

### **9. Don’t Include the Data Type in the Name**
- **Avoid Hungarian Notation:** Don’t prefix the variable name with its type (e.g., `strName`, `intAge`).

**Examples:**
```csharp
string name;              // Valid (no type prefix)
int age;                  // Valid (no type prefix)
```

**Invalid Examples:**
```csharp
string strName;           // Invalid (prefix 'str' is unnecessary)
int intAge;               // Invalid (prefix 'int' is unnecessary)
```

---

### **Summary Table of Examples**

| **Rule/Convention**                     | **Valid Example**          | **Invalid Example**         |
|-----------------------------------------|----------------------------|-----------------------------|
| Alphanumeric + Underscore               | `int studentCount;`        | `int student#Count;`        |
| Starts with Letter or Underscore        | `string _address;`         | `string 123value;`          |
| Case-Sensitive                          | `int value; int Value;`    | `int value; int value;`     |
| No Keywords                             | `int number;`              | `int int;`                  |
| Camel Case                              | `string firstName;`        | `string FirstName;`         |
| Avoid Underscores                       | `int score;`               | `int _score;` (unless private) |
| Descriptive Names                       | `int numberOfStudents;`    | `int x;`                    |
| No Contractions/Abbreviations           | `string customerName;`     | `string custNm;`            |
| No Type Prefixes                        | `string name;`             | `string strName;`           |

---

### **Understanding Implicitly Typed Local Variables (`var`) in C#**

#### **What is `var`?**
The `var` keyword allows the C# compiler to **infer** the data type of a variable based on its initial value. Once inferred, the variable behaves exactly as if it were explicitly declared with the actual data type.

---

### **Key Rules for Using `var`**
1. **Must Be Initialized:**
   - The variable must be assigned a value at the time of declaration.
   - Example:
     ```csharp
     var message = "Hello World!"; // Valid
     ```
     **Error Example:**
     ```csharp
     var message; // Invalid (no initialization)
     ```
     **Error Message:**
     ```
     error CS0818: Implicitly-typed variables must be initialized
     ```

2. **Type is Locked After Inference:**
   - Once the type is inferred, the variable cannot hold values of a different type.
   - Example:
     ```csharp
     var message = "Hello World!";
     message = 10.703m; // Invalid
     ```
     **Error Message:**
     ```
     error CS0029: Cannot implicitly convert type 'decimal' to 'string'
     ```

3. **Type is Obvious from Context:**
   - Use `var` when the type is clear from the initialization value.
   - Example:
     ```csharp
     var number = 42;          // Infers int
     var price = 19.99m;       // Infers decimal
     var name = "Alice";       // Infers string
     ```

---

### **Why Use `var`?**

1. **Reduces Keystrokes:**
   - Simplifies code when the type is obvious.
   - Example:
     ```csharp
     var longTypeName = new Dictionary<string, List<int>>(); // Cleaner than writing the full type
     ```

2. **Dynamic Planning:**
   - Useful during development when the exact type isn't immediately known.

3. **Common in Modern Codebases:**
   - Widely adopted in the C# community, so understanding `var` is essential.

---

### **When to Avoid `var`**
- **Beginner-Friendly Advice:** Use explicit types (`int`, `string`, etc.) when learning to ensure clarity and purposefulness.
- **Ambiguous Cases:** Avoid `var` when the type isn't immediately clear.
  - Example:
    ```csharp
    var result = SomeComplexFunction(); // Unclear what type `result` is
    ```

---

### **Examples of `var` Usage**

#### **Valid Examples:**
```csharp
var greeting = "Hello";        // Infers string
var age = 25;                  // Infers int
var temperature = 98.6F;       // Infers float
var isActive = true;           // Infers bool
var numbers = new List<int>(); // Infers List<int>
```

#### **Invalid Examples:**
```csharp
var value;                     // Error: Must initialize
var name = "Alice";
name = 123;                    // Error: Cannot change type
```

---

### **Cheat Sheet**
```csharp
// Valid Uses of var
var name = "Alice";         // string
var score = 100;            // int
var price = 19.99m;         // decimal
var isActive = true;        // bool

// Invalid Uses of var
var value;                  // Error: Must initialize
var name = "Alice";
name = 123;                 // Error: Type mismatch
```

### Formatting Literal Strings in C Sharp

1. **Escape Sequences**  
   Use `\` to insert special characters like tabs (`\t`), new lines (`\n`), or quotes (`\"`).  
   ```csharp
   Console.WriteLine("Hello\tWorld!"); 
   // Output: Hello    World!
   
   Console.WriteLine("Line1\nLine2");  
   // Output: Line1
//         Line2

   Console.WriteLine("She said, \"Hi!\""); 
   // Output: She said, "Hi!"
   ```

2. **Backslash Escape (`\\`)**  
   Use `\\` to include a literal backslash in a string.  
   ```csharp
   Console.WriteLine("C:\\Users\\Name"); // Output: C:\Users\Name
   ```

3. **Verbatim Strings (`@`)**  
   Use `@` to preserve whitespace, formatting, and backslashes as-is.  
   ```csharp
   Console.WriteLine(@"C:\Users\Name"); 
   // Output: C:\Users\Name
   
   Console.WriteLine(@"Line1
   Line2"); 
   // Output: Line1
   //         Line2
   ```

4. **Unicode Characters (`\u`)**  
   Use `\u` followed by a four-character Unicode code to include special characters.  
   ```csharp
   Console.WriteLine("\u00A9"); 
   
   // Output: © (Copyright symbol)
   ```

5. **Note on Unicode Printing**  
   Unicode characters may not display correctly in all applications depending on font or encoding support.

---

### **Quick Cheat Sheet**
```csharp
// Escape Sequences
Console.WriteLine("Tab: Hello\tWorld!");
Console.WriteLine("Newline: Line1\nLine2");
Console.WriteLine("Quotes: She said, \"Hi!\"");

// Backslash Escape
Console.WriteLine("Path: C:\\Users\\Name");

// Verbatim String
Console.WriteLine(@"Preserve: C:\Users\Name");

// Unicode Characters
Console.WriteLine("Symbol: \u00A9"); // ©
```

### **String Concatenation in C#**

#### **What is String Concatenation?**
String concatenation combines two or more strings into a single string using the `+` operator.

---

### **Key Concepts and Examples**

1. **Concatenate Literal Strings and Variables**
   Combine a literal string with a variable.
   ```csharp
   string firstName = "Bob";
   string message = "Hello " + firstName;
   Console.WriteLine(message); // Output: Hello Bob
   ```

2. **Concatenate Multiple Variables and Literal Strings**
   Combine multiple variables and literal strings in one line.
   ```csharp
   string firstName = "Bob";
   string greeting = "Hello";
   string message = greeting + " " + firstName + "!";
   Console.WriteLine(message); // Output: Hello Bob!
   ```

3. **Avoid Intermediate Variables**
   Perform concatenation directly where needed to simplify code.
   ```csharp
   string firstName = "Bob";
   string greeting = "Hello";
   Console.WriteLine(greeting + " " + firstName + "!"); // Output: Hello Bob!
   ```

---

### **Quick Cheat Sheet**
```csharp
// Basic Concatenation
string name = "Alice";
Console.WriteLine("Hello " + name); // Output: Hello Alice

// Multiple Concatenations
string firstName = "Bob";
string lastName = "Smith";
Console.WriteLine("Full Name: " + firstName + " " + lastName); // Output: Full Name: Bob Smith

// Direct Concatenation Without Intermediate Variables
Console.WriteLine("Welcome " + firstName + " to the program!"); // Output: Welcome Bob to the program!
```

---



### **String Interpolation in C#**

#### **What is String Interpolation?**
String interpolation allows you to combine variables, expressions, and literal strings into a single formatted string. It uses the `$` prefix and `{}` placeholders for variables or expressions.

---

### **Key Concepts with Examples**

1. **Basic String Interpolation**
   Combine a variable with a literal string using `$` and `{}`.
   ```csharp
   string firstName = "Bob";
   string message = $"Hello {firstName}!";
   Console.WriteLine(message); // Output: Hello Bob!
   ```

2. **Interpolation with Multiple Variables**
   Combine multiple variables and literals in one line.
   ```csharp
   int version = 11;
   string updateText = "Update to Windows";
   string message = $"{updateText} {version}";
   Console.WriteLine(message); // Output: Update to Windows 11
   ```

3. **Avoid Intermediate Variables**
   Perform interpolation directly in the output statement.
   ```csharp
   int version = 11;
   string updateText = "Update to Windows";
   Console.WriteLine($"{updateText} {version}!"); // Output: Update to Windows 11!
   ```

4. **Combine Verbatim Literals and Interpolation**
   Use both `@` (verbatim literal) and `$` (interpolation) together for paths or special formatting.
   ```csharp
   string projectName = "First-Project";
   Console.WriteLine($@"C:\Output\{projectName}\Data"); // Output: C:\Output\First-Project\Data
   ```

---

### **Quick Cheat Sheet**
```csharp
// Basic Interpolation
string name = "Alice";
Console.WriteLine($"Hello {name}!"); // Output: Hello Alice!

// Multiple Variables
int age = 25;
Console.WriteLine($"Name: {name}, Age: {age}"); // Output: Name: Alice, Age: 25

// Direct Interpolation Without Variables
Console.WriteLine($"Welcome {name} to the program!"); // Output: Welcome Alice to the program!

// Verbatim + Interpolation
string folder = "Logs";
Console.WriteLine($@"C:\Data\{folder}\File.txt"); // Output: C:\Data\Logs\File.txt
```

---

### **Key Takeaways**
- Use `$` for string interpolation and `{}` for placeholders.
- Combine `@` and `$` for verbatim literals with interpolation.
- Avoid intermediate variables unless they improve readability.
- String interpolation is cleaner and more concise than concatenation, especially for complex messages.