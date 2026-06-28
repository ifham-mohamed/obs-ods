
2024-12-25 20:46

Status:

Tags:

- **Relevance to Interests**: The course focuses on Node.js, which is one of the skills you've shown interest in. It covers important aspects like measuring quality, implementing testing, and measuring code coverage in Node.js apps.
- **Skill Enhancement**: It delves into JavaScript fundamentals, testing frameworks, and code quality concepts, which can enhance your back-end web development skills.
- **Intermediate Level**: Given your interest in front-end and back-end development, this intermediate-level course should match your current skill level and help you advance further.

![[Pasted image 20241225204811.png]]

![[Pasted image 20241225223908.png]]


# Node Js - Testing and Code Quality

### What is code quality?

- **Code Quality Definition**: Quality code meets functional requirements and is free from deficiencies. It should be useful and maintainable.
- **Useful Code**: Flexible and reusable, making it applicable in multiple scenarios.
- **Maintainable Code**: Can be maintained by the original author and others, with clear design and intent. Peer reviews help ensure maintainability.
- **Improvement**: Aim for continual, gradual improvements rather than radical overhauls to reduce risks.

![[Pasted image 20241225223933.png]]

1. Meeting functional requirements
2. Maintainable
3. Useful in multiple places


### Coding conventions and standards

![[Pasted image 20241225224312.png]]



- **Coding Conventions**: These are guidelines for writing programs in a particular language, focusing on programming style, practices, and methods.
- **Coding Standards**: A formal collection of coding conventions adopted by a group or organization to ensure quality and maintainability.
- **Programming Style Conventions**: Includes rules for comments, whitespace, naming conventions, and avoiding human errors to improve readability and maintainability.


#### Programming Style Conventions

1. Comments
2. Whitespace
3. Naming
4. Possible errors

### Creating and enforcing coding standards

- **Iterative Process**: Creating a coding standard is an iterative process. Start by determining available coding conventions, choose the ones that positively impact code quality and morale, document the justification, and regularly revisit the rules.
- **Team Involvement**: Involve the whole team in the decision-making process to ensure shared ownership and satisfaction with the coding standards.
- **Use of Linters**: Linters are tools that automatically enforce coding standards by scanning code for suspicious usage and coding convention violations. They provide fast, accurate, and consistent feedback, helping maintain code quality over time.

![[Pasted image 20241226124620.png]]

![[Pasted image 20241226124545.png]]


### Unit, integration, and functional testing
  

- **Unit Testing**: Tests the smallest parts of an application in isolation, focusing on individual methods or functions. It's fast and safe to run repeatedly.
![[Pasted image 20241226124903.png]]

- Tests isolated unit via API
- Performed in memory
- No permanent changes
- Safe to run repeatedly
- Fast execution

#### Assertion example

![[Pasted image 20241226125027.png]]


- **Integration Testing**: Combines multiple units and tests them together, including user interfaces and databases. It ensures that different parts of the application work well together.
![[Pasted image 20241226141210.png]]

![[Pasted image 20241226141236.png]]


- **Functional Testing**: Focuses on the results and user interface, comparing the outcomes against the specifications. It tests complete user workflows and can be automated or manual.

![[Pasted image 20241226141315.png]]

![[Pasted image 20241226141344.png]]

- **System Testing**: Involves testing the complete system, including the application and its environment. This can include performance, security, usability, and compatibility testing.  
![[Pasted image 20241226141429.png]]

![[Pasted image 20241226141453.png]]


- **Regression Testing**: Ensures that changes or updates to the code do not break existing functionality. This involves re-running unit and integration tests after changes are made.
![[Pasted image 20241226141519.png]]


![[Pasted image 20241226141546.png]]




![[Recording 2024-12-26 141922.mp4]]

### Testing frameworks

![[Pasted image 20241226234352.png]]


- **Purpose of Testing Frameworks**: They automate test execution, control the order of tests, and report results, making testing more efficient and maintainable.
- **Benefits**: Testing frameworks provide consistency in test structure and results, reduce maintenance costs, and allow developers to focus on writing tests rather than maintaining testing software.
- **Phases of Testing**: The four phases are setup (preparing the application state), execution (performing the target behavior), validation (comparing results with expected outcomes), and cleanup (restoring the application state).
- **Examples of Node.js Testing Frameworks**: Mocha, Jasmine, and Jest are common frameworks used for testing in Node.js environments.

![[Pasted image 20241226234427.png]]


![[Pasted image 20241226234527.png]]


![[Pasted image 20241226234908.png]]


![[Pasted image 20241226234927.png]]

![[Pasted image 20241226234946.png]]

![[Pasted image 20241226235004.png]]

![[Pasted image 20241226235023.png]]

![[Pasted image 20241226235141.png]]

Node.js Testing Frameworks
- Mocha — mochajs.org
- Jasmine — jasmine.github.io
- Jest — jestjs.io

![[Pasted image 20241227115204.png]]


### TDD and BDD test specifications

![[Pasted image 20241228103005.png]]

- **Test-Driven Development (TDD)**: This is a software development process where software requirements are turned into test cases before the software is improved to pass those tests. It focuses on creating a feedback loop for the developer.



- **Behavior-Driven Development (BDD)**: BDD uses a similar approach to TDD but focuses on using a more descriptive vocabulary to describe the behavior and intent of the software. It frames tests as scenarios with a structure like "Given, When, Then".

Acceptance Criteria as a Scenario
• Given some initial context (the givens)
• When an event occurs
• Then ensure some outcomes



![[Pasted image 20241228103145.png]]

![[Pasted image 20241228103218.png]]
![[Pasted image 20241228103251.png]]

![[Pasted image 20241228103323.png]]

![[Pasted image 20241228103417.png]]


- **Differences**: While TDD uses terminology around testing, BDD uses terminology around behavior and examples, which can lead to more understandable and maintainable tests.


### Assertions for correctness

![[Pasted image 20241228103515.png]]

![[Pasted image 20241228103634.png]]

- **Assertion Libraries**: Collections of assertions that validate the correctness of code, supporting comparisons of various language structures like objects, arrays, and numbers.

![[Pasted image 20241228103658.png]]


- **Types of Assertions**: Examples include checking if something is defined, if an object has a specific property, or if a promise resolves to a particular value.

![[Pasted image 20241228104441.png]]


- **Chaining Assertions**: Improves readability by allowing assertions to be written in a natural language style, making the code easier to understand and maintain.

![[Pasted image 20241228110109.png]]

![[Pasted image 20241228110137.png]]

### Challenge: Organize your tests

- **Types of Tests**: The video discusses four major types of tests: unit tests, integration tests, functional tests, and system tests.
- **Test Locations**: Tests can be located either outside of the project or within the project.
- **Naming Conventions**: Different naming conventions for test files include `FILE.test.js`, `TARGET-loadtest.js`, a test directory with a workflow, and a test directory with a route.

![[Pasted image 20241228110315.png]]

### Solution: Organize your tests

- **Unit Tests**: Test the smallest pieces of code and are typically located within the project, often in the same directory as the file being tested.
![[Pasted image 20241228110419.png]]

- **Integration Tests**: Combine multiple units and are usually located within the project, often against specific API routes.
![[Pasted image 20241228110440.png]]

- **Functional Tests**: Can involve services like databases and larger pieces of the application, and can be located both within and outside the project.
![[Pasted image 20241228110512.png]]

- **System Tests**: Exercise the entire application and are most likely located outside the project, such as load tests.
![[Pasted image 20241228110529.png]]



Standardizing with EditorConfig":  
  

- **EditorConfig**: A system that defines and maintains consistent coding styles across different text editors, focusing mainly on white space usage.
- **File Format and Plugins**: It consists of a file format (.editorconfig) that defines coding styles and a text editor plugin that enforces these styles.
- **Advantages**: Standardizing coding styles improves code quality by minimizing inconsistencies. EditorConfig is widely supported and used by many open-source projects like Node.js, jQuery, and React.
- **Configuration**: The configuration file is human-readable, flexible, and supports various properties like indent style, end-of-line format, character encoding, and more.


![[Pasted image 20241228113101.png]]


![[Pasted image 20241228113300.png]]

![[Pasted image 20241228113339.png]]

![[Pasted image 20241228113434.png]]

![[Pasted image 20241228113456.png]]

![[Pasted image 20241228113526.png]]

![[Pasted image 20241228113552.png]]

![[Pasted image 20241228113624.png]]

![[Pasted image 20241228113657.png]]



![[Pasted image 20241228123940.png]]


### Installing ESLint

- **Avoid Global Installation**: Installing ESLint globally is not recommended due to version conflicts and plugin management issues.
- **Project Installation**: It's best to install ESLint within your project as a development dependency using `npm install eslint --save-dev`.
- **Using npx**: Use `npx` to run ESLint without needing a global installation, ensuring consistency across different projects.
- **No Task Runners Needed**: ESLint can run independently without task runners like Gulp or Grunt. You can use `package.json` scripts for additional configurations

![[Pasted image 20241228124158.png]]

![[Pasted image 20241228124214.png]]


# Reference