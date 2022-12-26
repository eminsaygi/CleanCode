✽ Clean Code by Robert C. Martin

➽ Chapter 1 - Clean Code

This Book is about good programming. It's about how to write good code, and how to transform bad code into good code.
The code represents the detail of the requirements and the details cannot be ignored or abstracted. We may create languages that are closer to the requirements. We can create tools that help us parse and assemble those requirements into formal structures. But we will never eliminate necessary precision.

Why write bad code?

The previous arguments could create a swamp of senseless code.
If you say "I will back to fix it later" you could fall in the LeBlanc's law "Later equals never"
You are a professional and the code is your responsibility. Let's analyze the following anecdote:
What if you were a doctor and had a patient who demanded that you stop all the silly hand-washing in preparation for surgery because it was taking too much time? Clearly the patient is the boss; and yet the doctor should absolutely refuse to comply. Why? Because the doctor knows more than the patient about the risks of disease and infection. It would be unprofessional (never mind criminal) for the doctor to comply with the patient.
So too it is unprofessional for programmers to bend to the will of managers who don’t understand the risks of making messes.
Maybe sometime you think in go fast to make the deadline. The only way to go fast is to keep the code as clean as possible at all times.

What is Clean Code?
Each experimented programmer has his/her own definition of clean code, but something is clear, a clean code is a code that you can read easily. The clean code is code that has been taken care of.

In his book Uncle Bob says the next:
Consider this book a description of the Object Mentor School of Clean Code. The techniques and teachings within are the way that we practice our art. We are willing to claim that if you follow these teachings, you will enjoy the benefits that we have enjoyed,
and you will learn to write code that is clean and professional. But don’t make the mistake of thinking that we are somehow “right” in any absolute sense. There are other schools and other masters that have just as much claim to professionalism as we. It would behoove you to learn from them as well.

The boy Scout Rule
It’s not enough to write the code well. The code has to be kept clean over time. We have all seen code rot and degrade as time passes. 
So we must take an active role in preventing this degradation.

Always leave the campground cleaner than you found it.


Chapter 2 - Meaningful Names

Names are everywhere in software. Files, directories, variables functions, etc. Because we do so much of it. We have better do it well.

Use Intention-Revealing Names
It is easy to say that names reveal intent. Choosing good names takes time, but saves more than it takes. So take care with your names and change them when you find better ones.

The name of a variable, function or class, should answer all the big questions. It should tell you why it exists, what it does,
and how is used. If a name requires a comment, then the name does not reveals its intent.

Chapter 3 - Functions

The first rule of functions is that they should be small. The second rule of functions is that they should be smaller than that.

➥ Blocks and Indenting
This implies that the blocks within if statements, else statements, while statements, and so on should be one line long. Probably that line should be a function call. Not only does this keep the enclosing function small, but also adds documentary value because the function called within the block can have a nicely descriptive name.
This also implies that functions should not be large enough to hold nested structures. Therefore, the indent level of a function should not be greater than one or two. This, of course, makes the functions easy to read and understand.     

Chapter 4 - Comments

Nothing can be quite so helpful as a well-placed comment. Nothing can clutter up a module more than frivolous dogmatic comments. 
Nothing can be quite so damaging as an old comment that propagates lies and misinformation.

If our programming languages were expressive enough, or if we had the talent to subtly wield those languages to express our intent,
we would not need comments very much—perhaps not at all.



❂ Comments Do Not Make Up for Bad Code
Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments. 
Rather than spend your time writing the comments that explain the mess you’ve made, spend it cleaning that mess.


➽ Chapter 5 - Formatting

Code formatting is important. It is too important to ignore and it is too important to treat religiously. 
Code formatting is about communication, and communication is the professional developer’s first order of business.

√ Vertical Formatting
Vertical Openness Between Concepts
This concept consist in how to you separate concepts in your code, In the next example we can appreciate it.



Chapter 6 - Objects and Data Structures

☯ Data Abstraction
Hiding implementation is not just a matter of putting a layer of functions between the variables.
 Hiding implementation is about abstractions! A class does not simply push its variables out through getters and setters. 
 Rather it exposes abstract interfaces that allow its users to manipulate the essence of the data, without having to know its implementation.

☯ Data/Object Anti-Symmetry
These two examples show the difference between objects and data structures. Objects hide their data behind abstractions and expose functions that operate on that data. Data structure expose their data and have no meaningful functions.



➽ Chapter 7 - Error Handling

Many code bases are completely dominated by error handling. 
When I say dominated, I don't mean that error handling is all that they do. I mean that it is nearly impossible to see what the code does because of all of the scattered error handling. 
Error handling is important, but if it obscures logic, it's wrong.

〤 Use Exceptions Rather Than Return Codes
Back in the distant past there were many languages that didn't have exceptions.
In those languages the techniques for handling and reporting errors were limited. 
You either set an error flag or returned an error code that the caller could check


〤 Write Your Try-Catch-Finally Statement First
In a way, try blocks are like transactions.
Your catch has to leave your program in a consistent state, no matter what happens in the try. 
For this reason it is good practice to start with a try-catch-finally statement when you are writing code that could throw exceptions. 
This helps you define what the user of that code should expect, no matter what goes wrong with the code that is executed in the try.


➽ Chapter 8 - Boundaries

We seldom control all the software in our systems. 
Sometimes we buy third-party pack- ages or use open source. 
Other times we depend on teams in our own company to produce components or subsystems for us. Somehow we must cleanly integrate this foreign code with our own.

〥 Using Third-Party Code
There is a natural tension between the provider of an interface and the user of an interface. Providers of third-party packages and frameworks strive for broad applicability so they can work in many environments and appeal to a wide audience. Users, on the other hand, want an interface that is focused on their particular needs. This tension can cause problems at the boundaries of our systems.


Chapter 9 - Unit Tests


Test Driven Development

☑ The Three Laws of TDD
First Law You may not write production code until you have written a failing unit test.
Second Law You may not write more of a unit tests than is sufficient to fail, and not comipling is failing.
Third Law You may not write more production code than is sufficient to pass the currently failing tests.

☑Clean Tests
If you don't keep your tests clean, you will lose them.

☑ The readability it's very important to keep clean your tests.

☑ One Assert per test
It's recomendable maintain only one asserts per tests, because this helps to maintain each tests easy to understand.

☑ Single concept per Test ==> This rule will help you to keep short functions.
Write one test per each concept that you need to verify


☑ F.I.R.S.T
✓ Fast Test should be fast.
✓ Independient Test should not depend on each other.
✓ Repeatable Test Should be repeatable in any environment.
✓ Self-Validating Test should have a boolean output. either they pass or fail.
✓ Timely Unit tests should be written just before the production code that makes them pass. If you write tests after the production code, then you may find the production code to be hard to test.


 Chapter 10 - Classes

✇ Encapsulation
We like to keep our variables and utility functions small, but we're not fanatic about it.
 Sometimes we need to make a variable or utility function protected so that it can be accessed by a test.

✇ Classes Should be Small
- First Rule: Classes should be small
- Second Rule: Classes should be smaller than the first rule
- The Single Responsibility Principle
- Classes should have one responsibility - one reason to change

Chapter 11 - Systems

⌘ Separe Constructing a System from using It
Software Systems should separate the startuo process, when the application objects are constructed and the dependencies are "wired" thogether, from the runtime logic that takes over after startup

⌘ Separation from main
One way to separate construction from use is simply to move all aspects of construction to main, or modules called by main, and to design the rest of the system assuming that all objects have been created constructed and wired up appropriately.


Chapter 12 - Emergence

⍣ According to Kent Beck, a design is "simple" if it follows these rules

⍣ Run all tests
⍣ Contains no duplication
⍣ Expresses the intent of programmers
⍣ Minimizes the number of classes and methods

Chapter 13 - Concurrency

⌾ Concurrence is a decoupling strategy. It helps us decouple what gets fone from when it gets done. In single-threaded applications what and when are so strongly coupled that the state of the entire application can often be determined by looking at the stack backtrace. A programmer who debugs such a system can set a breakpoint, or a sequence of breakpoints, and know the state of the system by which breakpoints are hit.

⌾ Decoupling what from when can dramatically improve both the throughput and structures of an application. From a structural point of view the application looks like many lit- tle collaborating computers rather than one big main loop. This can make the system easier to understand and offers some powerful ways to separate concerns.

