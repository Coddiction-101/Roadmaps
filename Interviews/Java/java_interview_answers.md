# Java Interview Question Bank with Detailed Answers
### Comprehensive Answers for Self-Preparation

---

# 1. Java Fundamentals

## Variables & Data Types

**1. What is a variable?**
A variable is a named memory location that stores data which can be modified during program execution. It acts as a container for holding values of specific data types. In Java, every variable must be declared with a type before use, making Java a statically-typed language. Variables have scope (where they are accessible), lifetime (how long they exist), and visibility rules based on access modifiers.

**2. What is a data type?**
A data type defines the kind of value a variable can hold, the operations that can be performed on it, and how much memory it occupies. Java is strongly typed, meaning every variable and expression has a type known at compile time. Data types ensure type safety, prevent invalid operations, and help the compiler allocate appropriate memory.

**3. What are primitive data types in Java?**
Java has eight primitive data types: `byte` (8-bit signed integer), `short` (16-bit signed integer), `int` (32-bit signed integer), `long` (64-bit signed integer), `float` (32-bit floating-point), `double` (64-bit floating-point), `char` (16-bit Unicode character), and `boolean` (true/false). These are not objects and store values directly in stack memory for local variables.

**4. What are non-primitive data types?**
Non-primitive data types include classes, interfaces, arrays, and enums. They are reference types that store memory addresses (references) pointing to objects in heap memory. Unlike primitives, they have methods and can be null. String is technically a class (non-primitive) but has special language support.

**5. What is the difference between primitive and reference data types?**
Primitives store actual values directly in memory and have fixed sizes. Reference types store memory addresses pointing to heap objects. Primitives cannot be null, have no methods, and are compared using `==` for value equality. Reference types can be null, have methods, and `==` compares references, not content. Primitives are more memory-efficient and faster.

**6. Why is String not a primitive data type?**
String is a class (`java.lang.String`) that encapsulates a character array and provides numerous methods for manipulation. Being an object allows immutability, string pool optimization, and rich API support. Java provides literal syntax convenience, but String behaves as a reference type with special JVM handling.

**7. What is type casting?**
Type casting is explicitly converting a value from one data type to another. It tells the compiler to treat a value as a different type. Used when converting between compatible types where information might be lost or when the compiler cannot automatically determine the conversion is safe.

**8. What is implicit type casting?**
Implicit casting (widening) happens automatically when converting a smaller type to a larger type with no data loss. The compiler performs this safely: `byte -> short -> int -> long -> float -> double`, and `char -> int`. No explicit syntax is needed because the destination type can hold all values of the source type.

**9. What is explicit type casting?**
Explicit casting (narrowing) requires programmer intervention when converting a larger type to a smaller type where data loss may occur. Syntax: `(targetType) value`. Example: `int x = (int) 3.14;` results in `3`. The programmer takes responsibility for potential truncation or overflow.

**10. What is type promotion?**
Type promotion occurs during expression evaluation when smaller types are automatically promoted to larger types to prevent overflow. In mixed-type expressions, all operands are promoted to the largest type present. `byte` and `short` are always promoted to `int` in arithmetic operations, even when operating with each other.

**11. What happens when different data types are used in one expression?**
The compiler performs implicit promotion following these rules: if one operand is `double`, all become `double`; else if `float`, all become `float`; else if `long`, all become `long`; else all become `int`. This ensures precision is preserved but may require explicit casting if a smaller result type is desired.

**12. What is Unicode?**
Unicode is a universal character encoding standard that assigns a unique numeric value to every character across all writing systems, symbols, and emojis. It supports over 149,000 characters. UTF-16 encoding is used in Java's `char` type, allowing representation of characters from any language.

**13. Why does Java use Unicode?**
Java was designed for the global internet age, requiring support for all world languages. Unicode enables platform-independent character representation, internationalization, and consistent behavior across different operating systems and locales. It eliminates encoding issues when sharing text between systems.

**14. What is the default value of primitive data types?**
Numeric types default to `0` (or `0.0` for floating-point), `char` defaults to `'\u0000'` (null character), and `boolean` defaults to `false`. These defaults apply only to instance variables and array elements. Local variables must be explicitly initialized before use; otherwise, compilation fails.

**15. What is the difference between float and double?**
`float` is 32-bit single-precision with ~7 decimal digits of precision. `double` is 64-bit double-precision with ~15 decimal digits. `double` is the default floating-point type in Java. For scientific calculations or where precision matters, `double` is preferred. `float` requires the `f` suffix: `3.14f`.

**16. What is the difference between int and long?**
`int` is 32-bit, ranging from -2,147,483,648 to 2,147,483,647. `long` is 64-bit, ranging from -9 quintillion to +9 quintillion. Use `long` for timestamps, large counters, or when `int` overflow is possible. `long` literals require the `L` suffix: `10000000000L`.

**17. What is the size of each primitive data type?**
`byte`: 1 byte (8 bits), `short`: 2 bytes (16 bits), `int`: 4 bytes (32 bits), `long`: 8 bytes (64 bits), `float`: 4 bytes (32 bits), `double`: 8 bytes (64 bits), `char`: 2 bytes (16 bits), `boolean`: JVM-dependent (typically 1 byte in arrays, 4 bytes as local variables for alignment).

**18. Why is boolean size JVM-dependent?**
The Java Language Specification does not fix `boolean` size, allowing JVM implementations optimization flexibility. Typically, single booleans use 4 bytes (int-sized) for stack alignment, while `boolean[]` uses 1 byte per element. This trade-off optimizes memory versus access speed.

**19. What is a literal?**
A literal is a fixed, explicit value written directly in source code. It represents constant values of various types: integer literals (`42`), floating-point literals (`3.14`), character literals (`'A'`), string literals (`"Hello"`), and boolean literals (`true`, `false`).

**20. What are numeric literals?**
Numeric literals represent numbers in source code. Integer literals can be decimal (`42`), octal (`052`), hexadecimal (`0x2A`), or binary (`0b101010`). Floating-point literals can use decimal (`3.14`) or scientific notation (`3.14e2`). Underscores improve readability: `1_000_000`.

**21. What are character literals?**
Character literals represent single Unicode characters enclosed in single quotes: `'A'`, `'7'`, `'$'`. They can also represent characters via escape sequences (`'\n'`, `'\t'`) or Unicode escapes (`'\u0041'` for 'A'). The value is the 16-bit Unicode code point.

**22. What are escape sequences?**
Escape sequences are special character combinations starting with backslash that represent non-printable or reserved characters: `\n` (newline), `\t` (tab), `\r` (carriage return), `\\` (backslash), `\'` (single quote), `\"` (double quote), `\b` (backspace), `\f` (form feed).

**23. What is a constant?**
A constant is a variable whose value cannot change after initialization. In Java, constants are declared using the `final` keyword. By convention, constant names are uppercase with underscores: `final double PI = 3.14159;`. For true compile-time constants, use `static final`.

**24. What does final mean?**
`final` is a keyword that restricts modification. Applied to variables: value cannot change after assignment. Applied to methods: cannot be overridden by subclasses. Applied to classes: cannot be extended. Applied to reference variables: the reference cannot change, but the object's state can.

**25. Difference between final variable and constant?**
A `final` variable is immutable after assignment but may be instance-specific. A constant is typically `static final`, meaning it belongs to the class (not instances), is initialized at declaration or in static blocks, and is shared across all instances. Constants are compile-time evaluated when possible.

**26. Can a final reference variable change its object?**
No. A `final` reference variable cannot be reassigned to point to a different object. However, the internal state of the object it references can be modified if the object is mutable. For true immutability, both the reference must be `final` and the object itself must be immutable.

**27. What happens if a final variable is not initialized?**
Instance `final` variables must be initialized at declaration, in an instance initializer block, or in every constructor. Static `final` variables must be initialized at declaration or in a static block. Failure to initialize causes a compile-time error. Local `final` variables must be initialized before use.

---

# 2. Operators

**28. What are operators?**
Operators are special symbols that perform operations on operands (variables, literals, or expressions). They are the building blocks of computations and logic in Java, enabling arithmetic, comparison, logical, bitwise, and assignment operations.

**29. What are arithmetic operators?**
Arithmetic operators perform mathematical operations: `+` (addition, also string concatenation), `-` (subtraction, also unary negation), `*` (multiplication), `/` (division), `%` (modulo/remainder). Integer division truncates toward zero. The `+` operator with a String triggers concatenation, converting other operands to strings.

**30. What are relational operators?**
Relational operators compare two values and return a boolean result: `==` (equal to), `!=` (not equal to), `<` (less than), `>` (greater than), `<=` (less than or equal), `>=` (greater than or equal). They work on numeric types, characters, and booleans (only `==` and `!=`). For objects, `==` compares references, not content.

**31. What are logical operators?**
Logical operators combine boolean expressions: `&&` (logical AND, short-circuit), `||` (logical OR, short-circuit), `!` (logical NOT). Short-circuit evaluation means the second operand is evaluated only if necessary. `&&` stops if the first operand is false; `||` stops if the first operand is true.

**32. What are assignment operators?**
Assignment operators assign values to variables: `=` (simple assignment), `+=`, `-=`, `*=`, `/=`, `%=` (compound assignment). Compound operators perform the operation and assign in one step, with implicit casting: `x += 3` is equivalent to `x = (type of x)(x + 3)`, useful for byte/short operations.

**33. What are bitwise operators?**
Bitwise operators manipulate individual bits: `&` (AND), `|` (OR), `^` (XOR), `~` (NOT/complement), `<<` (left shift), `>>` (right shift with sign extension), `>>>` (unsigned right shift). They operate on integer types and are used for flags, masks, and low-level optimizations.

**34. What are shift operators?**
Shift operators move bits left or right: `<<` shifts left, filling with zeros (equivalent to multiplying by 2^n). `>>` shifts right, preserving the sign bit (arithmetic shift, equivalent to dividing by 2^n). `>>>` shifts right, always filling with zeros (logical shift, for unsigned interpretation).

**35. What is the ternary operator?**
The ternary operator `?:` is a concise conditional expression: `condition ? valueIfTrue : valueIfFalse`. It evaluates the condition and returns one of two values based on the result. It is right-associative and can be nested, though readability suffers with excessive nesting.

**36. What is operator precedence?**
Operator precedence determines the order in which operators are evaluated when multiple operators appear in an expression without parentheses. Higher precedence operators are evaluated first. Parentheses override precedence. Postfix operators have highest precedence, followed by unary, multiplicative, additive, shift, relational, equality, bitwise AND, XOR, OR, logical AND, logical OR, ternary, and assignment (lowest).

**37. What is associativity?**
Associativity determines the evaluation order when multiple operators of the same precedence appear. Most operators are left-associative (evaluated left to right): `a - b - c` is `(a - b) - c`. Assignment and ternary operators are right-associative: `a = b = c` is `a = (b = c)`.

**38. Difference between ++i and i++?**
`++i` (pre-increment) increments the variable first, then returns the new value. `i++` (post-increment) returns the current value first, then increments. In standalone statements, both behave identically. In expressions, the difference matters: `int x = ++i;` gives the incremented value; `int x = i++;` gives the original value.

**39. Difference between --i and i--?**
`--i` (pre-decrement) decrements first, returns new value. `i--` (post-decrement) returns current value, then decrements. The behavior mirrors pre-increment and post-increment. Both are efficient as they compile to direct CPU increment/decrement instructions.

**40. Difference between & and &&?**
`&` is the bitwise AND operator (also logical AND for booleans without short-circuit). `&&` is the logical AND with short-circuit evaluation. For booleans, both produce the same truth table, but `&&` skips evaluating the second operand if the first is false, saving computation and preventing potential errors.

**41. Difference between | and ||?**
`|` is the bitwise OR operator (also logical OR without short-circuit). `||` is the logical OR with short-circuit evaluation. `||` skips evaluating the second operand if the first is true. Both produce the same result for booleans, but `||` is more efficient and safer when the second operand has side effects or could cause errors.

**42. What is short-circuit evaluation?**
Short-circuit evaluation means the second operand of `&&` or `||` is evaluated only if the first operand does not determine the result. For `&&`, if the first operand is false, the entire expression is false regardless of the second. For `||`, if the first operand is true, the entire expression is true. This prevents unnecessary computation and null pointer exceptions.

**43. What happens in division by zero?**
Integer division by zero throws `ArithmeticException` at runtime. Floating-point division by zero does not throw an exception; instead, it produces special IEEE 754 values: `Infinity` (positive number divided by zero), `-Infinity` (negative number divided by zero), or `NaN` (zero divided by zero).

**44. What happens in floating-point division by zero?**
Floating-point division by zero follows IEEE 754 standards: positive value / 0.0 = `Infinity`, negative value / 0.0 = `-Infinity`, 0.0 / 0.0 = `NaN`. These are valid floating-point values, not exceptions. Subsequent operations with `Infinity` or `NaN` propagate these special values according to defined rules.

**45. Why is NaN generated?**
`NaN` (Not a Number) is generated by invalid floating-point operations: 0.0/0.0, `Infinity - Infinity`, square root of negative numbers (`Math.sqrt(-1)`), and other undefined mathematical operations. `NaN` is not equal to any value, including itself (`NaN == NaN` is false). Use `Double.isNaN()` to test for it.

---

# 3. Input & Output

**46. What is Scanner?**
`Scanner` is a class in `java.util` that parses primitive types and strings from various input sources using regular expressions. It breaks input into tokens using delimiters (default: whitespace) and provides `nextXxx()` methods for type-specific parsing. It is convenient but slower for large input compared to `BufferedReader`.

**47. How does Scanner work internally?**
`Scanner` reads input into an internal buffer, uses regular expressions to find delimiters, and parses tokens into requested types. It caches the input source, maintains position state, and uses locale-aware parsing. The underlying implementation uses `Readable` interface and `Pattern` matching.

**48. Difference between next() and nextLine()?**
`next()` reads the next token (delimited by whitespace) and returns it as a String. `nextLine()` reads the entire line up to and including the newline character, then returns the line without the newline. After `next()`, the newline remains in the buffer, causing `nextLine()` to read an empty string if called immediately after.

**49. Why does nextLine() sometimes skip input?**
After `nextInt()`, `nextDouble()`, or other `nextXxx()` methods, the newline character remains in the input buffer. A subsequent `nextLine()` reads this remaining newline as an empty string. Fix: call an extra `nextLine()` after numeric input to consume the newline, or use `nextLine()` for all input and parse manually.

**50. What is BufferedReader?**
`BufferedReader` is a character input stream that reads text from a character-input stream, buffering characters for efficient reading. It provides `readLine()` for line-by-line reading. It is significantly faster than `Scanner` for large input because it avoids regex parsing overhead and uses efficient buffering.

**51. Difference between Scanner and BufferedReader?**
`Scanner` is easier to use with built-in type parsing, uses regex, is slower, and handles various input sources. `BufferedReader` is faster, only reads strings (requires manual parsing), uses larger buffers, and is preferred for competitive programming and large file processing. `Scanner` is convenient; `BufferedReader` is performant.

**52. Which is faster: Scanner or BufferedReader?**
`BufferedReader` is significantly faster, often 5-10x faster for large inputs, because it avoids regular expression overhead and uses efficient character buffering. `Scanner` parses each token with regex, which is computationally expensive. For competitive programming or batch processing, `BufferedReader` with `StringTokenizer` or manual parsing is preferred.

**53. What is System.in?**
`System.in` is a standard input stream (`InputStream`) connected to the keyboard by default. It reads raw bytes from the console. `Scanner` and `BufferedReader` wrap `System.in` to provide character-level reading: `new Scanner(System.in)` or `new BufferedReader(new InputStreamReader(System.in))`.

**54. What is System.out?**
`System.out` is a standard output stream (`PrintStream`) connected to the console by default. It provides `print()`, `println()`, and `printf()` methods for output. It is buffered and automatically flushed on newline. It can be redirected to files or other streams.

**55. What is System.err?**
`System.err` is a standard error stream (`PrintStream`) also connected to the console. It is used for error messages and diagnostics, separate from normal output. In some environments, `System.err` output appears in a different color or is logged separately. It is unbuffered for immediate error display.

**56. What is PrintWriter?**
`PrintWriter` is a character-based output class that writes formatted representations of objects to a text-output stream. Unlike `PrintStream`, it handles character encoding properly. It provides `print()`, `println()`, `printf()`, and `format()` methods. It does not throw `IOException` directly; check `checkError()` instead.

---

# 4. Conditional Statements

**57. What is an if statement?**
An `if` statement is a conditional control structure that executes a block of code only if a specified boolean expression evaluates to true. It is the fundamental decision-making construct in Java, allowing programs to respond differently based on conditions.

**58. What is an if-else statement?**
An `if-else` statement provides two paths: the `if` block executes if the condition is true, otherwise the `else` block executes. It handles binary decisions. The `else` block is optional. Multiple statements in either block must be enclosed in braces; single statements can omit braces (though braces are recommended).

**59. What is nested if?**
A nested `if` is an `if` statement inside another `if` statement. It allows checking multiple conditions in a hierarchical manner. Each inner `if` is only evaluated if its outer `if` condition is true. Nesting can become complex; consider `else-if` ladders or switch statements for readability.

**60. What is else-if ladder?**
An `else-if` ladder (or `if-else-if` chain) checks multiple conditions sequentially. When a condition is true, its block executes and the rest are skipped. If no condition is true, the final `else` block executes (if present). It is cleaner than deeply nested `if` statements for mutually exclusive conditions.

**61. What is switch statement?**
A `switch` statement selects one of many code blocks to execute based on the value of an expression. It compares the expression value against `case` constants and jumps to the matching case. It is more readable than long `if-else-if` chains for discrete value matching.

**62. Difference between if-else and switch?**
`if-else` evaluates boolean expressions and handles ranges, complex conditions, and multiple variables. `switch` matches discrete values (integer types, enums, strings) and is more efficient for many equality checks. `if-else` is more flexible; `switch` is more readable and potentially faster due to jump table optimization.

**63. Which data types can be used in switch?**
Java 5+: `byte`, `short`, `int`, `char`, and their wrapper classes plus `enum` types. Java 7+: `String` added. Java 17+: pattern matching for `switch` (preview) allows more types. `long`, `float`, `double`, and `boolean` cannot be used directly in traditional switch statements.

**64. What is switch expression?**
Introduced in Java 14 (standard in Java 14+), `switch` expressions return a value and use arrow syntax (`->`) without fall-through. They can be assigned to variables: `int result = switch(x) { case 1 -> 10; case 2 -> 20; default -> 0; };`. They must be exhaustive or have a default.

**65. What is fall-through?**
Fall-through occurs when a `case` block in a traditional `switch` does not end with `break`, causing execution to continue into the next `case` block regardless of its match. This can be intentional for grouped cases but is usually a bug. Always use `break` unless fall-through is explicitly intended.

**66. What is break in switch?**
`break` terminates the `switch` statement, transferring control to the statement following the switch. Without `break`, execution falls through to subsequent cases. In `switch` expressions (arrow syntax), `break` is not needed as each case has a single expression and no fall-through occurs.

**67. Can switch work with Strings?**
Yes, since Java 7, `switch` supports `String`. The string's `hashCode()` is used for efficient lookup, with `equals()` for verification. The string must be non-null; a null value throws `NullPointerException`. String comparison is case-sensitive.

**68. When should switch not be used?**
Avoid `switch` when: conditions involve ranges or inequalities, complex boolean logic is needed, the variable type is unsupported (`long`, `double`, `boolean`), or there are only 2-3 cases (use `if-else` instead). For many cases with complex logic, polymorphism or strategy pattern may be better.

---

# 5. Loops

**69. What is a loop?**
A loop is a control structure that repeatedly executes a block of code as long as a condition remains true. Loops enable iteration over collections, processing until a condition is met, and performing repetitive tasks without code duplication. Java provides `for`, `while`, and `do-while` loops.

**70. What is a for loop?**
A `for` loop combines initialization, condition, and increment/decrement in a single line: `for (init; condition; update)`. It is ideal when the number of iterations is known beforehand. The initialization executes once, the condition is checked before each iteration, and the update executes after each iteration.

**71. What is a while loop?**
A `while` loop evaluates a condition before each iteration and executes the loop body only while the condition is true. It is ideal when the number of iterations is unknown and depends on runtime conditions. The condition may never be true, resulting in zero iterations.

**72. What is a do-while loop?**
A `do-while` loop executes the body first, then checks the condition. It guarantees at least one execution. The condition is evaluated after each iteration. Syntax: `do { body } while (condition);`. The semicolon after `while` is required.

**73. Difference between while and do-while?**
`while` checks the condition before the first iteration (zero or more executions). `do-while` checks after the first iteration (one or more executions). Use `while` when the body might not need to run. Use `do-while` when the body must run at least once, such as menu-driven programs.

**74. What is an enhanced for loop?**
The enhanced `for` loop (for-each) iterates over arrays or collections without explicit index management: `for (Type item : collection)`. It is cleaner, eliminates off-by-one errors, and works with any `Iterable`. However, it cannot modify the collection during iteration and has no access to the index.

**75. What is an infinite loop?**
An infinite loop never terminates because its condition always remains true or has no condition. Examples: `while (true)`, `for (;;)`, or a condition that never becomes false. Infinite loops are useful for servers, event loops, and waiting for external events, but accidental infinite loops cause program hangs.

**76. How can an infinite loop occur accidentally?**
Common causes: forgetting to update the loop variable, incorrect condition logic, modifying the loop variable in the wrong direction, or external state that never changes. Example: `int i = 0; while (i < 10) { System.out.println(i); }` never increments `i`.

**77. Difference between break and continue?**
`break` immediately exits the entire loop or switch, transferring control to the statement following the loop. `continue` skips the remaining code in the current iteration and proceeds to the next iteration's condition check. Both can use labels for nested loop control.

**78. Can labeled breaks be used?**
Yes, labeled `break` and `continue` can target specific outer loops in nested structures. A label is an identifier followed by a colon before the loop: `outer: for (...) { inner: for (...) { break outer; } }`. This exits the `outer` loop, not just the inner one.

**79. What are nested loops?**
Nested loops are loops inside other loops. The inner loop completes all its iterations for each single iteration of the outer loop. Common for matrix operations, pattern printing, and comparing all pairs. Time complexity is typically O(n^2) for doubly nested loops over n elements.

**80. What is loop optimization?**
Loop optimization improves performance by: minimizing work inside loops, moving invariant computations outside, using appropriate data structures, avoiding method calls in tight loops, leveraging compiler optimizations, and parallelizing independent iterations. Profile before optimizing; premature optimization is often unnecessary.

---

# 6. Arrays

**81. What is an array?**
An array is a fixed-size, ordered collection of elements of the same type, stored in contiguous memory locations. It provides O(1) access by index. Arrays are objects in Java, created with `new`, and their length is fixed at creation. The length is accessed via the `length` field (not a method).

**82. Why are arrays fixed in size?**
Arrays are fixed in size because memory is allocated contiguously at creation. This enables O(1) index-based access via pointer arithmetic. Resizing would require allocating new memory and copying all elements, which is expensive. For dynamic sizing, use `ArrayList` or other collections.

**83. How are arrays stored in memory?**
Array elements are stored in contiguous memory locations in the heap. The array reference (stored in stack for local variables) points to the array object header in heap, which contains length and type information, followed by the contiguous element data. This layout enables fast index-based access.

**84. What is array indexing?**
Array indexing is accessing an element by its position (index), starting from 0. The index represents the offset from the array's base address. Valid indices are 0 to `length-1`. The JVM performs bounds checking on every access, throwing `ArrayIndexOutOfBoundsException` for invalid indices.

**85. Why do arrays start at index 0?**
Zero-based indexing simplifies address calculation: `address = base_address + index * element_size`. Index 0 means no offset. It also aligns with modular arithmetic and pointer arithmetic in C, from which Java inherits conventions. Zero-based indexing is standard in most programming languages.

**86. What is ArrayIndexOutOfBoundsException?**
This runtime exception occurs when attempting to access an array element with an index outside the valid range (negative or >= length). It is an unchecked exception that indicates a programming error. Always validate indices or use loop bounds that respect `array.length`.

**87. How do you copy arrays?**
Methods: manual loop iteration, `System.arraycopy()` (native, fast), `Arrays.copyOf()` (creates new array of specified length), `Arrays.copyOfRange()` (copies a subrange), `clone()` (shallow copy for single-dimensional arrays), or `arraycopy` from `java.lang.System`.

**88. Difference between shallow copy and deep copy?**
Shallow copy duplicates the array structure but references the same underlying objects. Changes to objects affect both arrays. Deep copy duplicates both the array and all objects it contains, creating independent copies. For primitives, both are equivalent. For objects, implement `Cloneable` or copy constructors.

**89. What is a multidimensional array?**
A multidimensional array is an array of arrays. In Java, it is implemented as an array where each element is a reference to another array. `int[][] matrix` creates an array of array references. Rows can have different lengths (jagged arrays). Memory is not strictly contiguous across rows.

**90. What is a jagged array?**
A jagged array is a multidimensional array where each row can have a different length. Unlike rectangular arrays in C/C++, Java's multidimensional arrays are arrays of arrays, so each sub-array is independently allocated. Example: `int[][] jagged = new int[3][]; jagged[0] = new int[5]; jagged[1] = new int[3];`

**91. Difference between array and ArrayList?**
Arrays are fixed-size, part of the language, can hold primitives and objects, have `length` field, and are faster for primitive operations. `ArrayList` is dynamic-size, part of Collections Framework, holds only objects (autoboxing for primitives), has `size()` method, provides rich methods, and is more flexible.

**92. How do you find duplicates in an array?**
Approaches: nested loop comparison (O(n^2), O(1) space), sorting then checking adjacent elements (O(n log n), O(1) or O(n) space), HashSet tracking (O(n), O(n) space), or using a boolean array for limited ranges. Choose based on constraints: time, space, and whether the array can be modified.

**93. How do you reverse an array?**
Use two pointers: one at the start, one at the end, swap elements, and move pointers inward until they meet. This is O(n) time and O(1) space. For a new reversed array, iterate from the end and copy to a new array (O(n) space).

**94. How do you rotate an array?**
Left rotation by k: reverse first k elements, reverse remaining elements, then reverse the entire array. Right rotation is similar. This is O(n) time and O(1) space. Alternatively, use a temporary array or juggling algorithm (GCD-based cycles).

**95. How do you merge arrays?**
Create a new array of combined size, copy elements from both arrays. For sorted arrays, use a two-pointer merge like merge sort's merge step for O(n+m) time. For unsorted arrays, simple concatenation is O(n+m). System.arraycopy can efficiently copy blocks.

**96. How do you find the second largest element?**
Traverse once, tracking the largest and second largest. Initialize both to minimum values. For each element, if it exceeds largest, update second largest to old largest and largest to current. If it is between largest and second largest, update second largest. Handle edge cases (all same, fewer than 2 elements).

**97. How do you remove duplicates?**
For sorted arrays: two-pointer technique where a slow pointer tracks unique elements and a fast pointer scans ahead. For unsorted arrays: use a HashSet to track seen elements, then compact the array. If order matters and space is limited, sorting first may be necessary.

---

# 7. Strings

**98. What is a String?**
A `String` is an immutable sequence of characters, implemented as a `char[]` (or `byte[]` in Java 9+ for compact strings) with a rich API. It is a final class in `java.lang`, meaning it cannot be subclassed. Strings are widely used and have special JVM support including the String Pool.

**99. Why are Strings immutable?**
Immutability provides: security (sensitive data cannot be modified), synchronization safety (thread-safe without synchronization), hashcode caching (enables reliable HashMap/HashSet usage), string pool efficiency (same literal can be reused), and prevention of subversion (parameters cannot be altered after passing).

**100. What is String Pool?**
The String Pool (String Intern Pool) is a special memory region in the heap where string literals are stored and reused. When a string literal is created, the JVM checks the pool; if an identical string exists, the reference is reused. This saves memory when the same string appears multiple times. `intern()` can add strings to the pool explicitly.

**101. How does String Pool improve performance?**
By reusing identical string literals, the String Pool reduces memory consumption and allocation overhead. Instead of creating new objects for each literal occurrence, references point to the same pooled object. This is especially effective for commonly used strings, configuration values, and constants.

**102. Difference between String and StringBuilder?**
`String` is immutable; every modification creates a new object. `StringBuilder` is mutable; modifications happen in place without creating new objects. `StringBuilder` is faster for concatenation in loops but not thread-safe. `String` is safer for sharing but inefficient for frequent modifications.

**103. Difference between StringBuilder and StringBuffer?**
`StringBuilder` (Java 5+) is not synchronized, making it faster for single-threaded use. `StringBuffer` is synchronized (thread-safe) but slower due to locking overhead. For most cases, use `StringBuilder`. Use `StringBuffer` only when multiple threads modify the same builder.

**104. Difference between == and equals()?**
`==` compares references (memory addresses) for objects, checking if two references point to the same object. `equals()` compares content/logical equality. For `String`, `equals()` checks character-by-character equality. `==` may return true for string literals due to pooling, but false for `new String()` objects with the same content.

**105. What is intern()?**
`intern()` returns a canonical representation from the String Pool. If the string exists in the pool, that reference is returned. Otherwise, it is added to the pool. This enables `==` comparison for content equality when both strings are interned. Useful for reducing memory when many duplicate strings exist.

**106. What happens when String concatenation occurs?**
Using `+` with strings creates a new `String` object (immutable). In loops, this creates many intermediate objects. The compiler optimizes simple concatenation into `StringBuilder` operations, but explicit `StringBuilder` is better for complex or loop-based concatenation. Java 9+ uses `StringConcatFactory` for optimization.

**107. Why is String immutable but StringBuilder mutable?**
`String` is designed for safety, sharing, and caching. Immutability enables the String Pool, thread safety, and reliable hash codes. `StringBuilder` is designed for efficient modification, accepting the trade-off of mutability for performance. Different use cases demand different designs.

**108. What is substring()?**
`substring(int beginIndex)` returns a new string from the specified index to the end. `substring(int beginIndex, int endIndex)` returns the range [beginIndex, endIndex). In Java 7u6+, `substring` creates a new `char[]` copy (safer, no memory leak). Earlier versions shared the original `char[]`, causing potential memory issues.

**109. What is split()?**
`split(String regex)` divides a string into an array of substrings based on a regular expression delimiter. `split(String regex, int limit)` limits the number of resulting substrings. The regex is compiled each call; for repeated splitting, pre-compile with `Pattern`. Empty trailing strings may be discarded unless limit is negative.

**110. What is trim()?**
`trim()` removes leading and trailing whitespace characters (Unicode characters <= U+0020). It does not remove internal whitespace or all Unicode whitespace. For comprehensive whitespace handling, use `strip()` (Java 11+, handles all Unicode whitespace). `trim()` returns a new string since strings are immutable.

**111. How do you reverse a String?**
Approaches: manual character array swap (O(n), O(n) space), `StringBuilder.reverse()` (most practical), or recursive methods (elegant but O(n) stack space). For in-place reversal of a character array, use two pointers from both ends swapping characters.

**112. How do you check palindrome strings?**
Compare characters from both ends moving inward. If all mirrored pairs match, it is a palindrome. O(n) time, O(1) space. Alternatively, reverse the string and compare with original. Ignore case and non-alphanumeric characters based on requirements.

**113. How do you check anagrams?**
Anagrams have the same characters with the same frequencies. Approaches: sort both strings and compare (O(n log n)), or use frequency arrays/HashMaps (O(n)). For Unicode, HashMap is safer. Handle case sensitivity and whitespace based on requirements.

**114. How do you count character frequency?**
Use an array of size 256 (ASCII) or a `HashMap<Character, Integer>` for Unicode. Iterate through the string, incrementing counts. For sorted output, use a `TreeMap`. Time complexity is O(n), space is O(k) where k is the character set size.

**115. What is memory leakage related to Strings?**
In Java 6 and earlier, `substring()` shared the original `char[]`, so a small substring of a large string kept the entire original array in memory. This was fixed in Java 7u6 by copying the relevant portion. Large string concatenation in loops without `StringBuilder` can also cause excessive object creation and GC pressure.

---

# 8. Methods

**116. What is a method?**
A method is a named block of code that performs a specific task, encapsulating logic for reuse. Methods have a signature (name + parameters), a return type, and an optional access modifier. They promote code organization, reusability, and abstraction. Methods are defined within classes.

**117. Why are methods important?**
Methods enable code reuse (write once, use many times), abstraction (hide complexity), modularity (divide problems into manageable pieces), maintainability (changes in one place), and testing (isolated units). They are fundamental to structured and object-oriented programming.

**118. What are parameters?**
Parameters are variables declared in the method signature that act as placeholders for values passed when the method is called. They define what inputs the method expects. Parameters have types and names, and they are local to the method, initialized with argument values.

**119. What are arguments?**
Arguments are the actual values passed to a method when it is invoked. They are matched to parameters by position and must be compatible in type. Arguments can be literals, variables, or expressions. The number and types must match the method signature (or be compatible via implicit casting).

**120. Difference between parameters and arguments?**
Parameters are the formal variables in the method declaration (the definition). Arguments are the actual values passed during method invocation (the call). Parameters receive arguments. This distinction is important for understanding pass-by-value semantics.

**121. What is return type?**
The return type specifies the data type of the value a method returns to its caller. If a method returns no value, the return type is `void`. The `return` statement exits the method and passes back a value of the declared type. A method can have only one return type.

**122. What is method overloading?**
Method overloading allows multiple methods in the same class with the same name but different parameter lists (different number, types, or order of parameters). The compiler resolves which method to call based on the arguments. Overloading improves API usability with intuitive naming.

**123. What are rules for method overloading?**
Methods must differ in parameter list (number, type, or order). Return type alone does not distinguish overloaded methods. Access modifiers and exceptions do not affect overloading. Overloaded methods can have different return types if parameter lists differ. The compiler uses the most specific match.

**124. Can methods be overloaded using return type only?**
No. The compiler cannot distinguish methods by return type alone because the return type is not part of the method signature for invocation resolution. Calling `int result = method();` versus `double result = method();` would be ambiguous without parameter differences.

**125. What is recursion?**
Recursion is a technique where a method calls itself to solve a problem by breaking it into smaller subproblems. It requires a base case (termination condition) to prevent infinite recursion. Recursion is elegant for problems with recursive structure: trees, graphs, divide-and-conquer algorithms.

**126. What are advantages of recursion?**
Recursion produces clean, readable code for naturally recursive problems. It reduces complex problems to simpler subproblems. It eliminates the need for explicit stack management in many cases. It is intuitive for tree/graph traversal, backtracking, and divide-and-conquer algorithms like merge sort and quicksort.

**127. What are disadvantages of recursion?**
Recursion has overhead from repeated method calls and stack frame allocation. Deep recursion can cause `StackOverflowError`. It may be less efficient than iterative solutions due to function call overhead. Some problems are harder to reason about recursively. Memory usage grows with recursion depth.

**128. What is stack overflow?**
Stack overflow occurs when the call stack exceeds its allocated size, typically from infinite or excessively deep recursion. Each method call pushes a frame onto the stack; when the stack is full, the JVM throws `StackOverflowError`. The default stack size is platform-dependent, around 1MB.

**129. What is pass-by-value?**
Java is strictly pass-by-value. When a method is called, the argument values are copied into parameters. For primitives, the actual value is copied. For objects, the reference (memory address) is copied, not the object itself. This means the method cannot change the caller's variable reference, but can modify the object's state.

**130. Does Java support pass-by-reference?**
No. Java does not support pass-by-reference for method arguments. Some confusion arises because object references are passed by value, allowing method-side modifications to the object's state to be visible to the caller. However, the reference variable itself cannot be changed to point to a different object.

---

# 9. Classes & Objects

**131. What is a class?**
A class is a blueprint or template that defines the structure and behavior of objects. It encapsulates data (fields/variables) and operations (methods) that operate on that data. Classes are the fundamental building blocks of object-oriented programming in Java, enabling abstraction and encapsulation.

**132. What is an object?**
An object is a concrete instance of a class, created in memory with its own state. It has identity (unique address), state (field values), and behavior (methods). Objects are allocated in the heap memory. Multiple objects can be created from the same class, each with independent state.

**133. Difference between class and object?**
A class is a static blueprint/template; an object is a dynamic runtime instance. A class is declared once; many objects can be created from it. A class defines what exists; an object is what actually exists in memory. A class has no memory allocation; an object consumes memory.

**134. What is object instantiation?**
Instantiation is the process of creating an object from a class using the `new` keyword. It allocates memory in the heap, initializes fields to default values, calls the constructor, and returns a reference. Example: `Person p = new Person();` creates a new `Person` object.

**135. What is a reference variable?**
A reference variable stores the memory address (reference) of an object in the heap. It does not contain the object itself. Multiple reference variables can point to the same object. If no reference points to an object, it becomes eligible for garbage collection. Reference variables are stored on the stack.

**136. What is the new keyword?**
`new` is an operator that allocates memory for an object on the heap, initializes it, and returns a reference. It triggers constructor execution. Without `new`, no object is created. `new` can also create arrays. It is the primary mechanism for dynamic memory allocation in Java.

**137. What is object state?**
Object state is the collective values of all instance variables (fields) at a given moment. State represents the data or condition of an object. State changes through method calls and direct field access (if allowed). Encapsulation protects state by restricting direct access.

**138. What is object behavior?**
Object behavior is the set of actions an object can perform, defined by its methods. Behavior operates on and modifies state. Behavior represents what an object can do. Well-designed objects expose behavior while hiding internal state, following the principle of encapsulation.

**139. What are instance variables?**
Instance variables (fields) are declared within a class but outside any method. They belong to objects (instances), each object having its own copy. They are initialized to default values if not explicitly set. Their lifetime matches the object's lifetime. They represent object state.

**140. What are local variables?**
Local variables are declared within methods, constructors, or blocks. They exist only during method execution and are destroyed when the method exits. They must be explicitly initialized before use. They are stored on the stack, not the heap. They have no default values.

**141. What are static variables?**
Static variables (class variables) are declared with the `static` keyword. They belong to the class, not instances, and are shared across all objects. There is only one copy regardless of how many objects exist. They are initialized when the class is loaded and exist for the program's lifetime.

**142. What is an anonymous object?**
An anonymous object is created without assigning it to a reference variable. It is used for immediate, one-time use: `new Person().display()`. After the statement, the object has no reference and becomes eligible for garbage collection. Useful for single method calls but wasteful for objects needing multiple operations.

**143. What is object cloning?**
Cloning creates a copy of an object. Implement `Cloneable` interface and override `clone()` method from `Object`. The default `clone()` performs a shallow copy. For deep copies, manually copy all mutable fields. `clone()` is protected in `Object`; must be overridden as public.

**144. What is Object class?**
`Object` is the root class of all Java classes. Every class implicitly extends `Object`. It provides fundamental methods: `toString()`, `equals()`, `hashCode()`, `clone()`, `finalize()`, `getClass()`, `notify()`, `notifyAll()`, `wait()`. Understanding these methods is essential for proper object behavior.

---

# 10. Constructors

**145. What is a constructor?**
A constructor is a special method that initializes a newly created object. It has the same name as the class, no return type (not even `void`), and is called automatically when `new` is used. Constructors set up initial state, validate parameters, and prepare the object for use.

**146. Why are constructors used?**
Constructors ensure objects are created in a valid, consistent state. They initialize fields, allocate resources, validate inputs, and perform setup operations. Without constructors, objects would need manual initialization after creation, risking inconsistent states. Constructors enforce invariants from birth.

**147. Difference between constructor and method?**
Constructors have the same name as the class, no return type, and are called automatically on instantiation. Methods have arbitrary names, explicit return types (or `void`), and are called explicitly. Constructors cannot be inherited or overridden (though they can be overloaded). Methods can be called multiple times.

**148. What is a default constructor?**
A default constructor is a no-argument constructor provided by the compiler if no constructor is explicitly defined. It initializes fields to default values. If any constructor is defined, the compiler does not provide a default constructor. Best practice: always define an explicit no-arg constructor if needed.

**149. What is a parameterized constructor?**
A parameterized constructor accepts arguments to initialize object fields with specific values. It enables creating objects with custom initial state. Multiple parameterized constructors can be defined (overloading). They should validate parameters and throw exceptions for invalid inputs.

**150. What is constructor overloading?**
Constructor overloading defines multiple constructors with different parameter lists in the same class. This provides flexibility in object creation. The compiler selects the appropriate constructor based on arguments. Overloaded constructors often call each other using `this()` to avoid code duplication.

**151. Can constructors be inherited?**
No. Constructors are not inherited by subclasses. However, a subclass constructor can call a superclass constructor using `super()`. If not explicitly called, the compiler inserts `super()` as the first statement (calling the no-arg superclass constructor). If the superclass has no default constructor, the subclass must explicitly call an available constructor.

**152. Can constructors be overridden?**
No. Constructors cannot be overridden because they are not inherited. Overriding requires inheritance. A subclass can define its own constructors, which may call superclass constructors, but this is not overriding. Constructor names differ between classes (class name), so overriding is conceptually impossible.

**153. What is constructor chaining?**
Constructor chaining is calling one constructor from another in the same class (`this()`) or from a subclass constructor to a superclass constructor (`super()`). It reduces code duplication by reusing initialization logic. `this()` and `super()` must be the first statement and cannot coexist in the same constructor.

**154. What is this()?**
`this()` calls another constructor in the same class. It must be the first statement in the constructor. It enables constructor chaining, where a complex constructor reuses a simpler one's logic. It avoids duplicating initialization code across overloaded constructors.

**155. What is super()?**
`super()` calls a superclass constructor. If not explicitly written, the compiler inserts `super()` as the first statement of every subclass constructor (calling the no-arg superclass constructor). If the superclass lacks a no-arg constructor, an explicit `super(args)` call is required.

**156. Which executes first: this() or super()?**
Neither executes first relative to each other because they cannot appear in the same constructor. A constructor can have `this()` OR `super()` as its first statement, but not both. If neither is present, `super()` is implicitly inserted. The execution order is: superclass constructor -> instance variable initializers -> constructor body.

---

# 11. Encapsulation

**157. What is encapsulation?**
Encapsulation is the bundling of data (fields) and methods that operate on that data within a single unit (class), while restricting direct access to some components. It hides internal implementation details and exposes only controlled interfaces. It is achieved through access modifiers and getter/setter methods.

**158. Why is encapsulation important?**
Encapsulation protects data integrity by preventing unauthorized modification. It decouples implementation from interface, allowing internal changes without affecting users. It enables validation logic in setters. It supports invariants (rules that must always be true). It is a core principle of object-oriented design.

**159. How is encapsulation achieved?**
Encapsulation is achieved by: declaring fields as `private` (hidden from outside), providing public `getter` methods to read values, providing public `setter` methods to modify values (with validation), and keeping implementation details internal. This creates a controlled interface for object interaction.

**160. What are getters and setters?**
Getters (accessors) are methods that return field values: `public String getName()`. Setters (mutators) are methods that modify field values, often with validation: `public void setName(String name)`. They follow naming conventions and enable controlled access, computed properties, and change notification.

**161. What are access modifiers?**
Access modifiers control visibility and accessibility of classes, methods, and fields. Java provides four: `public` (accessible everywhere), `protected` (same package + subclasses), default/package-private (same package only), and `private` (same class only). They enforce encapsulation boundaries.

**162. Difference between public and private?**
`public` members are accessible from any class, anywhere. `private` members are accessible only within the declaring class. `public` exposes the API; `private` hides implementation. Fields should generally be `private`; methods can be `public` (API) or `private` (internal helpers).

**163. Difference between protected and default?**
`protected` members are accessible within the same package AND in subclasses (even in different packages). Default (no modifier) members are accessible only within the same package. `protected` enables inheritance-based access across packages; default restricts to package collaboration.

**164. How does encapsulation improve security?**
Encapsulation prevents direct manipulation of sensitive data. Validation in setters ensures only valid states are allowed. Internal invariants cannot be violated by external code. Implementation details can be changed without security implications. It enables audit logging and access control in getters/setters.

---

# 12. Inheritance

**165. What is inheritance?**
Inheritance is an OOP mechanism where a new class (subclass/derived class) acquires properties and behaviors from an existing class (superclass/base class). It promotes code reuse, establishes "is-a" relationships, and enables polymorphism. The `extends` keyword is used to establish inheritance.

**166. Why is inheritance used?**
Inheritance enables code reuse (common functionality in superclass, specialized in subclass), establishes natural hierarchies (Dog is an Animal), supports polymorphism (treating subclasses as superclass type), and promotes extensibility (new classes add features without modifying existing code). It models real-world relationships.

**167. What is extends keyword?**
`extends` is the keyword that establishes inheritance in Java. A subclass declaration: `class Dog extends Animal`. It means `Dog` inherits all non-private fields and methods from `Animal`. Java supports single inheritance for classes; a class can extend only one direct superclass.

**168. What is IS-A relationship?**
IS-A relationship represents inheritance: a subclass IS-A type of its superclass. `Dog IS-A Animal` means a Dog can be treated as an Animal. This enables polymorphism: `Animal a = new Dog();`. It should be used when the relationship is truly hierarchical, not just for code reuse.

**169. Types of inheritance?**
Java supports: single inheritance (one superclass per class), multilevel inheritance (A extends B, C extends A), and hierarchical inheritance (multiple subclasses from one superclass). Java does NOT support multiple inheritance with classes (to avoid ambiguity). Interfaces provide multiple inheritance of type.

**170. Why doesn't Java support multiple inheritance with classes?**
Multiple inheritance with classes creates ambiguity when two superclasses have methods with the same signature (the "diamond problem"). Java avoids this complexity by allowing single class inheritance. Interfaces provide a cleaner alternative for multiple inheritance of type without implementation ambiguity.

**171. What is multilevel inheritance?**
Multilevel inheritance is a chain where a class extends another class, which itself extends another: `C extends B extends A`. C inherits from both B and A (transitively). This creates deep hierarchies. While valid, excessive depth can make code hard to understand and maintain.

**172. What is hierarchical inheritance?**
Hierarchical inheritance occurs when multiple subclasses inherit from a single superclass: `B extends A`, `C extends A`, `D extends A`. All share common functionality from A while adding their own specializations. This is common in framework design and polymorphic collections.

**173. What is method overriding?**
Method overriding is redefining a superclass method in a subclass with the same signature (name, parameters, return type). The subclass provides specialized implementation. The overridden method is called based on the actual object's runtime type, not the reference type. Use `@Override` annotation for safety.

**174. Rules for overriding?**
The method must have the same name and parameter list. Return type must be the same or a covariant subtype (Java 5+). Access modifier cannot be more restrictive. Cannot throw broader checked exceptions. Must be an instance method (static methods are hidden, not overridden). Use `@Override` to catch errors.

**175. What is runtime polymorphism?**
Runtime polymorphism (dynamic method dispatch) is the mechanism where the method implementation to execute is determined at runtime based on the actual object's type, not the reference type. It enables calling subclass methods through superclass references. It is the foundation of flexible, extensible designs.

---

# 13. Polymorphism

**176. What is polymorphism?**
Polymorphism means "many forms." It is the ability of an object to take different forms or behave differently based on its context. In Java, it allows a superclass reference to refer to subclass objects and invoke overridden methods. It enables writing flexible, generic code that works with multiple types.

**177. Types of polymorphism?**
Compile-time polymorphism (static binding): method overloading, where the method to call is resolved at compile time based on parameters. Runtime polymorphism (dynamic binding): method overriding, where the method is resolved at runtime based on the actual object's type.

**178. Difference between overloading and overriding?**
Overloading: same class, same name, different parameters, compile-time resolution, return type can differ, access modifiers can differ, exceptions can differ. Overriding: different classes (inheritance), same signature, runtime resolution, return type must be same/covariant, access cannot be more restrictive, exceptions cannot be broader.

**179. What is compile-time polymorphism?**
Compile-time polymorphism is resolved during compilation. Method overloading is the primary example. The compiler determines which method to call based on the method signature (parameter types). It is also called static binding or early binding because the decision is made before runtime.

**180. What is runtime polymorphism?**
Runtime polymorphism is resolved during program execution. Method overriding is the primary example. The JVM determines which method implementation to invoke based on the actual object's class, not the reference type. It requires inheritance and enables dynamic behavior. Also called dynamic binding or late binding.

**181. What is dynamic method dispatch?**
Dynamic method dispatch is the mechanism by which a call to an overridden method is resolved at runtime rather than compile time. When a superclass reference points to a subclass object, calling an overridden method invokes the subclass version. This is the JVM's implementation of runtime polymorphism.

**182. What is upcasting?**
Upcasting is casting a subclass reference to a superclass type: `Animal a = new Dog();`. It is implicit and safe because a Dog is always an Animal. Upcasting enables polymorphism by allowing subclass objects to be treated as superclass instances. It restricts access to superclass members only.

**183. What is downcasting?**
Downcasting is casting a superclass reference back to a subclass type: `Dog d = (Dog) a;`. It is explicit and potentially unsafe because not every Animal is a Dog. Use `instanceof` to check before downcasting: `if (a instanceof Dog) { Dog d = (Dog) a; }`. Failure throws `ClassCastException`.

**184. Why is polymorphism useful?**
Polymorphism enables writing generic, reusable code that works with any subclass. It supports open-closed principle (open for extension, closed for modification). It simplifies code maintenance and enables frameworks to call user-defined implementations through standard interfaces. It is the foundation of many design patterns.

---

# 14. Abstraction

**185. What is abstraction?**
Abstraction is the concept of hiding complex implementation details and showing only essential features to the user. It focuses on "what" an object does rather than "how" it does it. Abstraction reduces complexity by providing a simplified interface and separates interface from implementation.

**186. Why is abstraction important?**
Abstraction manages complexity by hiding unnecessary details. It enables users to interact with systems without understanding internals. It supports modularity and separation of concerns. It allows implementation changes without affecting users. It is essential for building large, maintainable systems.

**187. What is an abstract class?**
An abstract class is a class declared with the `abstract` keyword that cannot be instantiated directly. It may contain abstract methods (without implementation) and concrete methods (with implementation). It serves as a base class for subclasses that provide implementations. It is a partial abstraction.

**188. What is an abstract method?**
An abstract method is declared with the `abstract` keyword and has no body. It ends with a semicolon. Subclasses must override and implement all abstract methods (unless the subclass is also abstract). Abstract methods define a contract that subclasses must fulfill.

**189. Can abstract classes have constructors?**
Yes. Abstract classes can have constructors, which are called when subclasses are instantiated (via `super()`). They initialize fields inherited by subclasses. Even though abstract classes cannot be instantiated directly, their constructors run during subclass object creation.

**190. Can abstract classes have concrete methods?**
Yes. Abstract classes can have both abstract and concrete methods. Concrete methods provide default implementations that subclasses can inherit or override. This is useful for shared functionality across all subclasses while leaving specific behaviors abstract.

**191. Difference between abstraction and encapsulation?**
Abstraction hides implementation complexity (showing only essential features). Encapsulation hides data by restricting access (bundling data with methods). Abstraction is about design (what to show). Encapsulation is about implementation (how to protect). They work together: encapsulation implements abstraction.

**192. When should abstract classes be used?**
Use abstract classes when: multiple related classes share common code, you want to provide default method implementations, you need to define non-public members (interfaces are public), you want to add methods without breaking existing implementations, or you need to maintain state (fields).

---

# 15. Interfaces

**193. What is an interface?**
An interface is a reference type that defines a contract of methods (and constants) that implementing classes must provide. It is a pure abstraction: all methods are implicitly abstract (until Java 8). A class implements an interface using the `implements` keyword. Interfaces enable multiple inheritance of type.

**194. Why use interfaces?**
Interfaces enable multiple inheritance of type (a class can implement multiple interfaces). They define contracts that unrelated classes can fulfill. They enable loose coupling (program to interfaces, not implementations). They support polymorphism across unrelated class hierarchies. They facilitate testing with mock implementations.

**195. Difference between interface and abstract class?**
Interface: all methods abstract (pre-Java 8), no state (pre-Java 8), multiple inheritance supported, methods implicitly public, variables implicitly public static final. Abstract class: can have concrete methods, can have state (fields), single inheritance only, any access modifiers, any variable types.

**196. What are default methods?**
Default methods (Java 8+) are interface methods with implementations using the `default` keyword. They allow adding methods to interfaces without breaking existing implementations. They provide backward compatibility. Implementing classes can override them. They enable interfaces to evolve without forcing all implementers to change.

**197. What are static methods in interfaces?**
Static methods (Java 8+) belong to the interface, not instances. They are called using the interface name: `InterfaceName.staticMethod()`. They provide utility methods related to the interface. They cannot be overridden. They are not inherited by implementing classes.

**198. What are functional interfaces?**
Functional interfaces are interfaces with exactly one abstract method (though they may have default and static methods). They are the foundation of lambda expressions. Examples: `Runnable`, `Comparator`, `Predicate`. Annotated with `@FunctionalInterface` to enforce the contract and catch errors.

**199. What is marker interface?**
A marker interface is an empty interface with no methods that marks classes for special treatment by the JVM or frameworks. Examples: `Serializable` (enables object serialization), `Cloneable` (allows object cloning), `Remote` (for RMI). The marker provides metadata that tools and runtime check via `instanceof`.

**200. What is multiple inheritance using interfaces?**
Java allows a class to implement multiple interfaces, achieving multiple inheritance of type. A class inherits method signatures from all interfaces and must provide implementations. If two interfaces have methods with the same signature, the class implements once, satisfying both. Default method conflicts must be resolved explicitly.

**201. What is @FunctionalInterface?**
`@FunctionalInterface` is an annotation that indicates an interface is intended to be a functional interface (exactly one abstract method). It is optional but recommended because it causes a compile error if the interface violates the contract (more than one abstract method). It documents intent and enables compiler verification.

---

# 16. Exception Handling

**202. What is an exception?**
An exception is an event that disrupts the normal flow of program execution. It represents an error or exceptional condition that occurs during runtime. Exceptions are objects in Java, instances of `Throwable` or its subclasses. They carry information about the error type, message, and stack trace.

**203. What is exception handling?**
Exception handling is the mechanism to gracefully manage runtime errors without crashing the program. It separates error-handling code from normal logic using `try-catch-finally` blocks. Proper handling allows programs to recover from errors, log them, and continue execution or fail gracefully.

**204. What is try block?**
A `try` block encloses code that might throw an exception. It defines the guarded region. If an exception occurs within the `try` block, control transfers to the matching `catch` block. The remaining code in `try` after the exception is skipped. A `try` must be followed by at least one `catch` or `finally`.

**205. What is catch block?**
A `catch` block handles exceptions thrown in the corresponding `try` block. It specifies the exception type to catch. Multiple `catch` blocks can handle different exception types. The first matching `catch` executes. Catch blocks should be ordered from most specific to most general (`Exception` last).

**206. What is finally block?**
A `finally` block contains code that executes regardless of whether an exception occurred. It runs after `try` completes normally or after `catch` handles an exception. It is used for cleanup: closing resources, releasing locks, restoring state. `finally` executes even if `return` or `break` occurs in `try`/`catch`.

**207. What is throw?**
`throw` is a keyword that explicitly raises an exception object. It transfers control to the nearest matching `catch` block in the call stack. Syntax: `throw new ExceptionType("message");`. It is used to signal error conditions detected by the program, such as invalid arguments or business rule violations.

**208. What is throws?**
`throws` in a method declaration indicates that the method may throw specified checked exceptions. It delegates responsibility for handling to the caller. The caller must either catch the exception or declare it in its own `throws` clause. `throws` is part of the method contract and API documentation.

**209. Difference between throw and throws?**
`throw` is a statement that creates and raises an exception object at runtime. `throws` is a clause in a method declaration that lists checked exceptions the method might throw. `throw` is an action; `throws` is a declaration. `throw` executes code; `throws` documents the contract.

**210. What are checked exceptions?**
Checked exceptions are exceptions that the compiler requires to be handled or declared. They represent recoverable conditions that a program should anticipate: `IOException`, `SQLException`, `ClassNotFoundException`. The compiler enforces `try-catch` or `throws` for these. They are subclasses of `Exception` but not `RuntimeException`.

**211. What are unchecked exceptions?**
Unchecked exceptions are exceptions that the compiler does not require handling. They represent programming errors that should not normally occur: `NullPointerException`, `ArrayIndexOutOfBoundsException`, `IllegalArgumentException`. They are subclasses of `RuntimeException` or `Error`. They indicate bugs that should be fixed, not caught.

**212. What is custom exception?**
A custom exception is a user-defined exception class extending `Exception` (checked) or `RuntimeException` (unchecked). It provides meaningful error types for application-specific conditions. Custom exceptions improve code readability and enable callers to catch specific business errors rather than generic exceptions.

**213. What is NullPointerException?**
`NullPointerException` occurs when code attempts to use an object reference that is `null`: calling a method on null, accessing a field of null, or throwing null. It is the most common runtime exception. Prevent it with null checks, `Optional` (Java 8+), or `@NonNull` annotations.

**214. What is ArithmeticException?**
`ArithmeticException` occurs for illegal arithmetic operations: integer division by zero. Floating-point division by zero does not throw this (produces Infinity/NaN). Other causes include overflow in certain contexts. It is an unchecked exception indicating a programming error or invalid input.

**215. What is ClassCastException?**
`ClassCastException` occurs when an object is cast to an incompatible type. Common cause: downcasting a superclass reference to a subclass without `instanceof` check. Example: `String s = (String) new Object();`. Prevent with `instanceof` checks before casting.

**216. What is NumberFormatException?**
`NumberFormatException` occurs when attempting to convert a string to a numeric type but the string has an invalid format. Example: `Integer.parseInt("abc")`. It is a subclass of `IllegalArgumentException`. Prevent by validating input before parsing or using `try-catch` with fallback values.

**217. What is exception propagation?**
Exception propagation is the process by which an uncaught exception moves up the call stack from the method where it occurred to its caller, then to the caller's caller, and so on, until caught or reaching the main method, where the JVM terminates the program and prints the stack trace.

---

# 17. Collections Framework (continued)

**245. What is load factor?**
The load factor is the ratio of the number of elements to the number of buckets (capacity). Default is 0.75. When the load factor is exceeded, the hash table is resized (rehashed). A higher load factor reduces memory usage but increases collision probability. A lower load factor improves performance but wastes memory.

**246. What is rehashing?**
Rehashing is the process of resizing the hash table and redistributing all existing entries into the new, larger table. When the number of elements exceeds capacity * load factor, a new table (typically double the size) is created, and each entry is reinserted using its hash code modulo the new capacity.

**247. Why is HashMap not synchronized?**
`HashMap` is not synchronized for performance reasons. Synchronization adds overhead from locking. For concurrent access, use `ConcurrentHashMap` (segmented locking), `Collections.synchronizedMap()` (coarse locking), or external synchronization. The unsynchronized design makes single-threaded use faster.

**248. Difference between HashMap and Hashtable?**
`HashMap`: not synchronized, allows null key and null values, faster, iterator is fail-fast. `Hashtable`: synchronized (thread-safe), no null keys or values, slower, enumerator is not fail-fast. `Hashtable` is legacy (Java 1.0); prefer `HashMap` or `ConcurrentHashMap`.

**249. Difference between HashMap and TreeMap?**
`HashMap`: unordered, O(1) average operations, hash-based, allows null key. `TreeMap`: sorted by key (natural order or Comparator), O(log n) operations, Red-Black tree-based, no null key. Use `HashMap` for fast lookup; `TreeMap` for sorted traversal or range queries.

**250. Difference between HashMap and LinkedHashMap?**
`HashMap`: no guaranteed order. `LinkedHashMap`: maintains insertion order (or access order if configured). `LinkedHashMap` uses a doubly-linked list connecting entries in insertion order. Slightly more memory overhead than `HashMap`. Use when iteration order must match insertion order.

---

# 18. File Handling

**251. What is file handling?**
File handling is the process of reading from and writing to files on the file system. Java provides classes in `java.io` and `java.nio` for file operations. File handling enables persistent data storage, configuration reading, log writing, and data exchange between programs.

**252. What is File class?**
`java.io.File` is an abstract representation of file and directory pathnames. It provides methods to create, delete, rename files, check existence, get properties (size, last modified), and list directory contents. It does not handle file content directly; use streams for reading/writing content.

**253. How do you create files?**
Use `File.createNewFile()` (returns boolean), `FileWriter` or `FileOutputStream` (creates if not exists), `Files.createFile()` (Java 7 NIO), or `PrintWriter`. Always handle `IOException`. Check if the file already exists to avoid overwriting. Ensure parent directories exist using `mkdirs()`.

**254. How do you read files?**
Approaches: `FileReader`/`BufferedReader` for character-based reading, `FileInputStream` for byte-based reading, `Files.readAllLines()` (Java 7 NIO, convenient for small files), `Scanner` for tokenized reading, or `Files.newBufferedReader()` for large files. Choose based on file size, format, and performance needs.

**255. How do you write files?**
Approaches: `FileWriter`/`BufferedWriter` for character writing, `FileOutputStream` for byte writing, `PrintWriter` for formatted output, `Files.write()` (Java 7 NIO), or `FileChannel` for large files. Always close resources (use try-with-resources). Flush buffers to ensure data is written.

**256. Difference between FileReader and BufferedReader?**
`FileReader` reads characters directly from a file, one character at a time (inefficient). `BufferedReader` wraps a reader and buffers characters for efficient reading, providing `readLine()` for line-by-line access. Always prefer `BufferedReader` over raw `FileReader` for performance.

**257. Difference between FileWriter and BufferedWriter?**
`FileWriter` writes characters directly to a file (inefficient for many small writes). `BufferedWriter` buffers output, reducing system calls and improving performance. It provides `newLine()` for platform-independent line endings. Always wrap `FileWriter` with `BufferedWriter` for better performance.

**258. What is serialization?**
Serialization is the process of converting an object into a byte stream that can be stored to a file, transmitted over a network, or saved to a database. The object must implement `java.io.Serializable`. The `ObjectOutputStream` class performs serialization. Transient fields and static fields are not serialized.

**259. What is deserialization?**
Deserialization is the reverse process: reconstructing an object from its serialized byte stream. `ObjectInputStream` reads the byte stream and creates a new object with the same state. The class must be available in the classpath. `serialVersionUID` ensures version compatibility between serialized and deserialized objects.

**260. Why is serialization used?**
Serialization enables object persistence (saving state between program runs), remote method invocation (RMI), distributed computing (sending objects over networks), caching, and deep cloning. It is a fundamental mechanism for Java's distributed and persistent object capabilities.

---

# 19. Packages

**261. What is a package?**
A package is a namespace that organizes related classes and interfaces into a logical group. It prevents naming conflicts (two classes can have the same name in different packages). It controls access (default access is package-private). It corresponds to a directory structure in the file system.

**262. Why are packages used?**
Packages organize code into logical modules, prevent class name collisions, control visibility (package-private access), enable reuse and distribution (JAR files), and support versioning. They are essential for building large applications and libraries. The reverse domain naming convention ensures global uniqueness.

**263. What is import?**
The `import` statement tells the compiler where to find classes that are not in the current package or `java.lang`. It does not include files or copy code; it simply provides fully qualified names. Static imports (`import static`) bring static members into scope. `import java.util.*` imports all classes in the package.

**264. Difference between built-in and user-defined packages?**
Built-in packages are provided by the JDK: `java.lang`, `java.util`, `java.io`, `java.net`. They are automatically available (except `java.lang` which is implicitly imported). User-defined packages are created by developers to organize their own code: `package com.company.project;`.

**265. What is package naming convention?**
Packages use reverse domain names to ensure global uniqueness: `com.company.project.module`. All lowercase, no hyphens (use underscores), no Java keywords. Example: `com.google.common.collect`. This prevents conflicts between libraries from different organizations.

---

# 20. Multithreading

**266. What is a thread?**
A thread is a lightweight subprocess, the smallest unit of execution within a process. Multiple threads share the same process resources (memory, file handles) but execute independently. Java threads are managed by the JVM and mapped to OS threads. Threads enable concurrent execution and responsive applications.

**267. Difference between process and thread?**
A process is an independent program with its own memory space. A thread is a path of execution within a process. Processes are isolated; threads share memory. Process creation is expensive; thread creation is cheaper. Context switching between processes is slower than between threads. A process can have multiple threads.

**268. What is multithreading?**
Multithreading is the concurrent execution of multiple threads within a single process. It enables parallel processing on multi-core CPUs and responsive UIs (background tasks don't freeze the interface). Java supports multithreading through the `Thread` class and `Runnable` interface.

**269. Why use multithreading?**
Multithreading improves performance on multi-core systems, increases application responsiveness, enables concurrent I/O operations, and supports real-time processing. It is essential for servers handling multiple clients, GUIs, and computationally intensive tasks that can be parallelized.

**270. Thread lifecycle?**
New: thread created but not started. Runnable: ready to run, waiting for CPU. Running: actively executing. Blocked/Waiting: waiting for a monitor lock or another thread's notification. Timed Waiting: waiting for a specified time. Terminated: execution completed or exception occurred. Transitions are controlled by start(), sleep(), wait(), notify(), join(), and synchronized blocks.

**271. Difference between Thread and Runnable?**
`Thread` is a class that implements `Runnable`. Extending `Thread` limits inheritance (Java single inheritance). Implementing `Runnable` is preferred because it separates the task from the execution mechanism, allows the same task to run on multiple threads, and preserves the option to extend another class.

**272. What is synchronization?**
Synchronization is the mechanism to control access to shared resources by multiple threads, preventing race conditions. It ensures that only one thread executes a critical section at a time. Achieved via `synchronized` methods/blocks, `ReentrantLock`, or atomic classes. Synchronization prevents data inconsistency but can reduce throughput.

**273. What is race condition?**
A race condition occurs when multiple threads access shared data concurrently, and the outcome depends on the timing of their execution. The final state is unpredictable. Example: two threads incrementing a counter simultaneously may result in lost updates. Prevented by synchronization or atomic operations.

**274. What is deadlock?**
Deadlock occurs when two or more threads are blocked forever, each waiting for a resource held by another. Four conditions must hold: mutual exclusion, hold and wait, no preemption, and circular wait. Prevent by: lock ordering (always acquire locks in the same order), timeout-based locking, or deadlock detection.

**275. What is starvation?**
Starvation occurs when a thread is perpetually denied access to resources because other threads always have higher priority or acquire locks first. The thread is ready to run but never gets CPU time. Prevent by using fair locks (`ReentrantLock(true)`), adjusting thread priorities, or ensuring balanced resource allocation.

**276. What is context switching?**
Context switching is the process of saving the state of a running thread and restoring the state of another thread. It involves saving registers, program counter, and stack pointer. Context switching has overhead; excessive switching reduces performance. The OS scheduler determines when to switch.

**277. What is thread safety?**
Thread safety means a class or method behaves correctly when accessed by multiple threads simultaneously. Thread-safe code uses synchronization, immutability, or atomic operations to prevent race conditions. Examples: `StringBuffer` (synchronized), `ConcurrentHashMap`, `AtomicInteger`. Non-thread-safe examples: `ArrayList`, `HashMap`, `StringBuilder`.

---

# 21. JVM, JRE & JDK

**278. What is JVM?**
The Java Virtual Machine (JVM) is an abstract computing machine that executes Java bytecode. It provides platform independence by translating bytecode to native machine code. The JVM handles memory management, garbage collection, security, and thread management. Each Java application runs in its own JVM instance.

**279. What is JRE?**
The Java Runtime Environment (JRE) is the minimum environment needed to run Java applications. It includes the JVM, core libraries (`rt.jar`), and supporting files. It does not include development tools like the compiler. End users need only the JRE to run Java programs.

**280. What is JDK?**
The Java Development Kit (JDK) is the full development environment for building Java applications. It includes the JRE, compiler (`javac`), debugger, documentation generator (`javadoc`), archiver (`jar`), and other development tools. Developers need the JDK to write, compile, and debug Java code.

**281. Difference between JVM, JRE and JDK?**
JVM: executes bytecode. JRE: JVM + libraries (run Java). JDK: JRE + development tools (build Java). Relationship: JDK contains JRE contains JVM. Analogy: JVM is the engine, JRE is the car, JDK is the car factory with tools to build cars.

**282. How does Java achieve platform independence?**
Java achieves platform independence through the "Write Once, Run Anywhere" principle. Java source code is compiled to bytecode (platform-independent), which runs on any JVM (platform-specific implementation). The JVM translates bytecode to native machine code for the host OS. This abstraction shields Java programs from OS differences.

**283. What is bytecode?**
Bytecode is the intermediate, platform-independent instruction set generated by the Java compiler (`javac`). It is not native machine code but a compact representation that the JVM interprets or compiles to native code (via JIT). Bytecode files have `.class` extension and are stored in the file system or JARs.

**284. What is class loader?**
The class loader is a subsystem of the JVM responsible for loading class files into memory. It uses delegation: Bootstrap (core JDK classes), Extension (extension libraries), and Application (classpath classes). Custom class loaders can be created. It performs verification, preparation, and resolution of classes.

**285. What is JIT compiler?**
The Just-In-Time (JIT) compiler compiles frequently executed bytecode to native machine code at runtime, improving performance over pure interpretation. HotSpot JVM identifies "hot" methods and compiles them. The compiled code is cached and reused. JIT provides near-native performance for long-running applications.

---

# 22. Memory Management

**286. What is stack memory?**
Stack memory stores local variables, method parameters, return addresses, and partial results. Each thread has its own stack. Memory is allocated and deallocated in LIFO order as methods are called and return. Stack is fast, automatically managed, and limited in size (typically 1MB per thread).

**287. What is heap memory?**
Heap memory is the runtime data area where all objects and arrays are allocated. It is shared across all threads. Memory is managed by the garbage collector. Heap is larger than stack but slower to allocate. Divided into Young Generation (new objects), Old Generation (long-lived objects), and Permanent/Metaspace (class metadata).

**288. Difference between stack and heap?**
Stack: stores primitives and references, LIFO allocation, fast, thread-private, automatic cleanup, fixed size, limited scope. Heap: stores objects and arrays, dynamic allocation, slower, shared across threads, garbage collected, large size, objects persist until GC. Primitives in objects are stored in heap with the object.

**289. What is garbage collection?**
Garbage collection is the automatic process of reclaiming memory occupied by objects that are no longer reachable (no references point to them). The JVM's garbage collector identifies and removes garbage objects, freeing memory for reuse. It eliminates manual memory management and prevents memory leaks (mostly).

**290. How does garbage collection work?**
Modern GC uses generational collection: Young Generation (Eden, Survivor spaces) uses fast copying algorithms for short-lived objects. Old Generation uses mark-sweep-compact for long-lived objects. When Eden fills, minor GC runs. When Old Generation fills, major GC (full GC) runs. The JVM pauses application threads during GC (stop-the-world).

**291. What is memory leak?**
A memory leak occurs when objects are no longer needed but remain referenced, preventing garbage collection. The heap gradually fills, causing performance degradation and eventual `OutOfMemoryError`. Common causes: static collections growing unbounded, unclosed resources, listeners not deregistered, and caches without eviction policies.

**292. What is OutOfMemoryError?**
`OutOfMemoryError` is thrown when the JVM cannot allocate an object because the heap is full and no more memory can be freed by garbage collection. Causes: memory leaks, insufficient heap size, large object allocations, or too many threads (each consumes stack space). Fix by increasing heap size or fixing leaks.

**293. What objects are eligible for garbage collection?**
Objects are eligible for GC when no live references point to them. This includes: objects whose references are set to null, objects that go out of scope, objects in isolated cycles (if no external reference exists), and objects only referenced by other eligible objects. The GC root set includes stack variables, static fields, and JNI references.

**294. Can garbage collection be forced?**
No, garbage collection cannot be truly forced. `System.gc()` and `Runtime.gc()` are merely suggestions to the JVM. The JVM may ignore them for performance reasons. Modern GCs are self-tuning and generally perform better when left to manage themselves. Forcing GC can cause unnecessary pauses.

**295. What is finalize()?**
`finalize()` is a method in `Object` called by the garbage collector before an object is destroyed. It allows cleanup of resources (closing files, releasing native resources). However, it is unreliable (may never be called), has performance issues, and is deprecated since Java 9. Prefer `try-with-resources` and `Cleaner` instead.

---

# 23. Scenario-Based Questions

**296. Your application suddenly becomes slow. What would you investigate first?**
First, identify the bottleneck: CPU (high processing load), memory (excessive GC, swapping), I/O (slow database queries, file operations), or network latency. Use profiling tools (JProfiler, VisualVM), check logs for errors, monitor JVM metrics (heap usage, GC frequency), analyze thread dumps for deadlocks, and review recent code changes. Start with the most likely cause based on symptoms.

**297. A HashMap lookup becomes slower than expected. Possible reasons?**
Possible causes: high load factor causing many collisions, poor `hashCode()` implementation clustering keys, concurrent modification causing infinite loops (pre-Java 8), too many entries in a single bucket (should treeify in Java 8+), or using mutable keys that change hash code after insertion. Solutions: increase initial capacity, improve hash distribution, ensure key immutability.

**298. Users report NullPointerExceptions in production. How would you debug?**
Enable detailed logging with stack traces. Use static analysis tools (SpotBugs, NullAway) to catch potential NPEs at build time. Add null checks with meaningful error messages. Use `Optional` to explicitly handle potentially null values. Review recent changes for uninitialized fields or unchecked external data. Use defensive programming: validate inputs, fail fast with clear messages.

**299. Multiple threads are updating shared data incorrectly. What could be happening?**
This is a race condition. The shared data lacks proper synchronization. Multiple threads read-modify-write without atomicity, causing lost updates. Solutions: use `synchronized` methods/blocks, `ReentrantLock`, atomic classes (`AtomicInteger`), or thread-safe collections (`ConcurrentHashMap`). Identify critical sections and protect them. Consider using immutable objects where possible.

**300. Your application is consuming too much memory. How would you investigate?**
Take heap dumps and analyze with tools like Eclipse MAT or VisualVM. Look for: memory leaks (unclosed collections, caches without limits), large object allocations, excessive string creation, unbounded caches, or static collections growing indefinitely. Monitor GC logs for frequent full GCs. Use profiling to find the largest objects and reference chains preventing GC.

**301. ArrayList insertion is slow. Why?**
Insertion in the middle or beginning of `ArrayList` is O(n) because elements must be shifted. Frequent resizing (when capacity is exceeded) causes array copying. If the list is large and insertions are frequent, consider `LinkedList` for O(1) insertions (with iterator), or pre-allocate capacity with `new ArrayList<>(expectedSize)`.

**302. LinkedList traversal is slow. Why?**
`LinkedList` has poor cache locality because nodes are scattered in memory. Each node access requires pointer chasing, causing cache misses. Random access is O(n) because traversal starts from the beginning (or end if closer). For frequent random access, `ArrayList` is preferred. Use `LinkedList` primarily for sequential access and frequent insertions/deletions.

**303. Which collection would you choose for unique elements and why?**
Use `HashSet` for O(1) add/contains/remove when order doesn't matter. Use `LinkedHashSet` when insertion order must be preserved. Use `TreeSet` when elements need to be sorted. All three enforce uniqueness via `equals()` and `hashCode()`. Choose based on whether you need ordering and what type of ordering.

**304. Which collection would you choose for key-value storage and why?**
Use `HashMap` for O(1) average operations when order doesn't matter. Use `LinkedHashMap` for insertion-order iteration. Use `TreeMap` for sorted keys and range queries. Use `ConcurrentHashMap` for thread-safe concurrent access. Use `Hashtable` only if working with legacy code (prefer `ConcurrentHashMap`).

**305. When would you use an interface over an abstract class?**
Use an interface when: multiple unrelated classes need to implement the contract, you need multiple inheritance of type, you want to define a capability (CanFly, Comparable), or you want loose coupling. Use an abstract class when: related classes share common code, you need default implementations, or you need to maintain state (fields). Since Java 8, the line has blurred with default methods.

---

# 24. Tricky Java Questions

**306. Why is String immutable?**
For security (sensitive data protection), thread safety (no synchronization needed), hashcode caching (reliable HashMap keys), string pool efficiency (reuse), and subversion prevention (parameters can't be altered after passing). Immutability enables these optimizations and guarantees.

**307. Why is String final?**
`String` is final so it cannot be subclassed. Subclasses could break immutability, hash code contract, or security guarantees. Finality ensures consistent behavior across all String instances and enables JVM optimizations like String Pool and inline caching.

**308. Can main() be overloaded?**
Yes, `main()` can be overloaded like any other method. However, the JVM only calls `public static void main(String[] args)` as the entry point. Other overloaded `main` methods are regular methods that must be called explicitly from the standard `main`.

**309. Can constructors be private?**
Yes, private constructors prevent external instantiation. Used in: singleton pattern (only one instance via static method), utility classes (all methods static, no instantiation needed), and factory method pattern (controlled object creation). A class with only private constructors cannot be subclassed (unless nested).

**310. Can abstract classes have constructors?**
Yes. Abstract class constructors are called when subclasses are instantiated. They initialize inherited fields. Even though abstract classes cannot be directly instantiated, their constructors run as part of the subclass construction chain via `super()`.

**311. Can interfaces have methods with implementation?**
Yes, since Java 8. Interfaces can have `default` methods (with implementation, can be overridden) and `static` methods (belong to interface, cannot be overridden). Java 9+ allows private methods in interfaces for code reuse within default methods.

**312. Why doesn't Java support multiple inheritance?**
To avoid the "diamond problem": ambiguity when two superclasses have methods with the same signature. Java allows single class inheritance but multiple interface implementation, which avoids implementation ambiguity while providing type polymorphism.

**313. Why doesn't Java support operator overloading?**
To maintain simplicity and readability. Operator overloading can make code confusing (e.g., `+` meaning addition or string concatenation). Java's designers prioritized clarity over syntactic sugar. The exception is `+` for string concatenation, which is built-in.

**314. Can we override static methods?**
No, static methods are hidden, not overridden. Hiding means the subclass method with the same signature shadows the superclass method. The method called depends on the reference type, not the object type. There is no runtime polymorphism for static methods.

**315. Can we override private methods?**
No. Private methods are not visible to subclasses, so they cannot be overridden. A subclass can define a method with the same name, but it is a new method, not an override. The `@Override` annotation would cause a compile error.

**316. Can we overload main()?**
Yes, `main()` can be overloaded. The JVM only recognizes `public static void main(String[] args)` as the entry point. Other overloaded versions are regular static methods that can be called from within the standard `main`.

**317. Can we make constructor final?**
No. Constructors cannot be final because they are not inherited, so overriding (which final prevents) is impossible. The `final` keyword is meaningless for constructors and causes a compile error.

**318. Can final methods be overridden?**
No. `final` methods cannot be overridden by subclasses. This ensures the method implementation remains consistent across the inheritance hierarchy. It is used for methods that must not be changed for security or correctness.

**319. Can final classes be inherited?**
No. `final` classes cannot be extended. This prevents modification of behavior through inheritance. Examples: `String`, `Math`, `System`. Finality ensures the class implementation cannot be subverted by malicious or buggy subclasses.

**320. Why is Object class parent of all classes?**
`Object` provides fundamental methods that every object needs: `toString()`, `equals()`, `hashCode()`, `getClass()`, `wait()`, `notify()`. By making `Object` the root, Java ensures all objects have these capabilities and can be treated uniformly (e.g., stored in `Object[]`, synchronized on any object).

---

# 25. Most Frequently Asked Fresher Questions

**321. Explain OOP concepts.**
Object-Oriented Programming has four pillars: (1) Encapsulation: bundling data and methods, hiding implementation. (2) Inheritance: acquiring properties from parent classes. (3) Polymorphism: many forms (overloading and overriding). (4) Abstraction: hiding complexity, showing essentials. These principles enable modular, reusable, maintainable code.

**322. Difference between overloading and overriding?**
Overloading: same class, same name, different parameters, compile-time resolution. Overriding: different classes (inheritance), same signature, runtime resolution. Overloading is about convenience; overriding is about specialization. Overloading changes the interface; overriding preserves it while changing implementation.

**323. Difference between HashMap and HashSet?**
`HashMap` stores key-value pairs; `HashSet` stores single elements. `HashSet` is implemented using `HashMap` internally (elements as keys, dummy values). `HashMap` allows one null key; `HashSet` allows one null element. Both use hashing for O(1) operations. `HashMap` is a Map; `HashSet` is a Set.

**324. Difference between ArrayList and LinkedList?**
`ArrayList`: dynamic array, O(1) random access, O(n) middle insertion, better cache locality. `LinkedList`: doubly-linked list, O(n) random access, O(1) insertion with iterator, worse cache locality. Use `ArrayList` for access-heavy workloads; `LinkedList` for insertion-heavy workloads.

**325. Difference between String, StringBuilder and StringBuffer?**
`String`: immutable, thread-safe, slow for modifications. `StringBuilder`: mutable, not thread-safe, fast. `StringBuffer`: mutable, thread-safe (synchronized), slower than `StringBuilder`. Use `String` for constants; `StringBuilder` for single-threaded modifications; `StringBuffer` for multi-threaded modifications (rarely needed now).

**326. Difference between interface and abstract class?**
Interface: contract-only (pre-Java 8), multiple inheritance, no state (pre-Java 8), all methods public. Abstract class: can have state and concrete methods, single inheritance, any access modifiers. Use interface for capabilities; abstract class for shared implementation. Since Java 8, interfaces can have default methods, blurring the line.

**327. Difference between checked and unchecked exceptions?**
Checked: compiler-enforced handling, represent recoverable conditions (IOException, SQLException), must catch or declare. Unchecked: compiler doesn't enforce, represent programming errors (NullPointerException, ArrayIndexOutOfBoundsException), should fix code rather than catch. Checked extends Exception; unchecked extends RuntimeException.

**328. Difference between JVM, JRE and JDK?**
JVM: executes bytecode. JRE: JVM + libraries (run Java). JDK: JRE + development tools (build Java). JDK contains JRE contains JVM. End users need JRE; developers need JDK.

**329. Difference between stack and heap?**
Stack: thread-private, stores local variables and references, LIFO, fast, automatic, limited size. Heap: shared, stores objects and arrays, dynamic allocation, garbage collected, larger, slower. Primitives in methods are on stack; objects are always on heap.

**330. Explain HashMap internal working.**
`HashMap` uses an array of buckets (Node[]). Each bucket is a linked list (or tree for large buckets). The bucket index is `hash(key) & (table.length - 1)`. Entries contain key, value, hash, and next pointer. When size exceeds load factor (0.75), the table resizes (doubles). Java 8 converts long lists to Red-Black trees for O(log n) worst case.

**331. Explain String Pool.**
The String Pool is a special heap area where string literals are stored and reused. When `"hello"` appears, the JVM checks the pool. If found, the existing reference is returned. If not, a new String is created and added to the pool. `intern()` can add strings explicitly. This saves memory when the same string appears multiple times.

**332. Explain Garbage Collection.**
GC automatically reclaims memory from unreachable objects. Modern JVMs use generational collection: Young Generation (Eden + Survivor) for short-lived objects with fast copying GC; Old Generation for long-lived objects with mark-sweep-compact. GC runs when memory is low. Full GC pauses all threads. Tuning involves heap size, generation ratios, and GC algorithm selection.

**333. Explain Collections Framework.**
The Collections Framework provides interfaces (List, Set, Map, Queue), implementations (ArrayList, HashMap, HashSet), and algorithms (sorting, searching). It offers unified, efficient, and interoperable ways to store and manipulate groups of objects. All implementations share common interfaces, enabling polymorphic code.

**334. Explain Multithreading basics.**
Multithreading enables concurrent execution within a process. Threads share memory but have separate stacks. Create threads by extending `Thread` or implementing `Runnable`. Synchronization prevents race conditions using `synchronized`, locks, or atomic classes. Challenges include deadlocks, race conditions, and thread safety. Java 5+ provides `java.util.concurrent` for advanced concurrency.

**335. Explain your Java project.**
[Personalize this answer based on your actual project. Structure: (1) Project name and purpose. (2) Technologies used (Java version, frameworks, libraries). (3) Architecture overview (MVC, layered, etc.). (4) Key features implemented. (5) Challenges faced and solutions. (6) Your specific contributions. (7) What you learned. Practice explaining clearly in 2-3 minutes.]

---

> **Study Tips:**
> - Read each answer and explain it aloud without looking.
> - Create flashcards for the most common questions (321-335).
> - Practice writing short answers for 10 questions daily.
> - Focus on "why" not just "what" — interviewers ask follow-ups.
> - Relate concepts to real-world examples when explaining.

---

**Last Updated:** June 2026
**Prepared For:** BCA Freshers targeting 3-5 LPA Java roles
**Recommended Use:** Daily revision, mock interviews, viva preparation
