# Strings

**Definition:**  
String is an object of class **java.lang.String**

---

## Creating Strings

### 1. Using new keyword (NOT recommended)

String s = new String();            // empty string  
String s = new String("hello!");  

---

### 2. Using char array (NOT recommended)

char[] cArray = {'h', 'e', 'l', 'l', 'o', '!'};
String s = new String(cArray);

---

### 3. Using String literal (RECOMMENDED)

String s = "hello!";

---

# Important Properties

- String uses **character array** to store text  
- Java uses **UTF-16** encoding  
- String is a **sequence of Unicode characters**  
- String is **immutable**

---

## Meaning of Immutable

- Once a String is created → **cannot be changed**
- Any modification creates a **new object**

---

## Example

String s = "hello";
s = s + " world";   // new object created

---

# String is Special

## 1. String Literal

String s = "hello";

---

## 2. + Operator (Concatenation)

String s = "hello" + " world!";  
// "hello world!"

---

## 3. String Pool (Memory Optimization)

- Java stores literals in **String Pool**
- Avoids duplicate objects → **saves memory**

---

## Example

String a = "hello";
String b = "hello";

- Both refer to **same memory location**

---

# Key Points

- Prefer **string literals** over new keyword  
- Strings are **immutable**  
- Stored in **String Pool**  
- Supports **concatenation using +**



# Regular Expressions (Regex) in Java

**Definition:**  
Regex is used to **search, match, and manipulate strings**.

---

## Common Methods in String

### 1. replace()

- Replaces **characters (literal)**

String s = "hello world";
String result = s.replace("o", "r");

Output: hellr wrrld

---

### 2. replaceAll()

- Uses **regex pattern**

String s = "hello world";
String result = s.replaceAll(".", "X");

Output: XXXXXXXXXXX

---

## Important Difference

| Method        | Uses Regex | Use Case              |
|--------------|----------|----------------------|
| replace()     | ❌ No    | simple replace       |
| replaceAll()  | ✅ Yes   | pattern-based replace|

---

# Special Regex Symbols

| Symbol | Meaning |
|-------|--------|
| .     | any character |
| \\d   | digit (0-9) |
| \\w   | word character |
| \\s   | whitespace |
| ^     | start of string |
| $     | end of string |
| []    | range |
| ()    | group |
| {}    | repetition |

---

# Example: Mask Credit Card

## Code

String creditCard = "1234567812345678";
String maskedCard = creditCard.replaceAll(".(?=.{4})", "X");

System.out.println(maskedCard);

---

## Output

XXXXXXXXXXXX5678

---

## Explanation

Pattern:

.(?=.{4})

- . → match any character  
- (?=...) → lookahead (check without consuming)  
- .{4} → last 4 characters  

👉 Meaning:  
Replace every character **except last 4**

---

# Example: Replace Dot

String s = "hello world";

s.replace(".", "X");        // no change (literal)
s.replaceAll(".", "X");     // all replaced

---

# Key Points

- replace() → simple text replace  
- replaceAll() → regex based  
- Regex is powerful for **validation & formatting**  
- Lookahead (?=...) is very important concept  


# String Literal vs Using new

---

## 1. String Literal

String s1 = "hello";
String s2 = "hello";
String s3 = s1;

### Properties

- Stored in **String Pool (heap)**
- Same values → **share same memory**
- Memory efficient

---

## 2. Using new Keyword

String s4 = new String("hello");
String s5 = new String("hello");

### Properties

- Stored as **separate objects in heap**
- No memory sharing
- Works like normal object

---

# Comparison

| Feature              | String Literal        | new String()        |
|---------------------|---------------------|--------------------|
| Memory location     | String Pool         | Heap               |
| Memory sharing      | ✅ Yes              | ❌ No              |
| Performance         | Faster              | Slower             |
| Recommended         | ✅ Yes              | ❌ No              |

---

# Important Example

String s1 = "hello";
String s2 = "hello";

System.out.println(s1 == s2);   // true (same reference)

---

String s4 = new String("hello");
String s5 = new String("hello");

System.out.println(s4 == s5);   // false (different objects)

---

# Key Concept

## == vs equals()

- `==` → compares **reference (memory address)**
- `.equals()` → compares **value**

---

## Example

String a = "hello";
String b = new String("hello");

System.out.println(a == b);        // false  
System.out.println(a.equals(b));   // true  

---

# Key Points

- Prefer **String literal**  
- String Pool saves memory  
- `new` always creates new object  
- Use `.equals()` for comparison  




# String Immutability

**Definition:**  
String value can **never be changed** after creation.

---

## Example

String s1 = new String("abcd");   // or "abcd"
s1 = new String("1234");          // old object is abandoned

---

## Key Concept

- Original string **remains unchanged**
- New string object is created
- Old object becomes eligible for **garbage collection**

---

# Why Immutability?

---

## 1. String Interning

- Strings are stored in **String Pool**
- Multiple references can share same object

Example:

String s1 = "hello";
String s2 = "hello";

👉 Both refer to same object

---

### Why needed?

- If String were mutable → one change affects all references ❌  
- Immutability ensures safe sharing ✅

---

## 2. Concurrency (Thread Safety)

- Multiple threads can use same String safely

Example:

Thread 1 → "hello"  
Thread 2 → "hello"  

👉 No risk of modification

---

## 3. Security

- Strings are used in sensitive areas:
  - File paths
  - Database URLs
  - Network connections

Example:

FileInputStream(String name)

👉 If mutable → attacker could change path ❌  
👉 Immutable → safe ✅

---

# Important Example

String s = "hello";
s.concat(" world");

System.out.println(s);   // still "hello"

---

## Why?

- concat() creates **new object**
- original string unchanged

---

# Key Points

- String is **immutable**
- Any change → new object created  
- Enables:
  - String Pool  
  - Thread safety  
  - Security  



  # StringBuilder

**Definition:**  
StringBuilder is a **mutable sequence of characters** (can be changed).

---

## Introduced

- From **Java 5**

---

## Example

StringBuilder sb = new StringBuilder();

sb.append("hello");
sb.append(" world!");

String s = sb.append(" Good")
             .append(" morning")
             .toString();

---

## Output

hello world! Good morning

---

## Common Methods

- append() → add text  
- length() → get length  
- delete() → remove part  
- insert() → insert text  
- reverse() → reverse string  
- replace() → replace characters  

---

## Key Feature

- Mutable → **modifies same object**
- Faster than String for multiple operations

---

# StringBuffer

**Definition:**  
Similar to StringBuilder but **thread-safe (synchronized)**

---

## Characteristics

- Synchronized → safe for multi-threading  
- Slower than StringBuilder  
- API same as StringBuilder  

---

## Recommendation

- ❌ StringBuffer → generally not needed  
- ✅ Use StringBuilder (faster)  

---

# Comparison

| Feature        | String           | StringBuilder      | StringBuffer       |
|---------------|----------------|-------------------|--------------------|
| Mutable       | ❌ No          | ✅ Yes            | ✅ Yes             |
| Thread-safe   | ❌ No          | ❌ No             | ✅ Yes             |
| Performance   | Slow           | Fast              | Slower             |

---

# Key Points

- Use **StringBuilder** for frequent modifications  
- Use **StringBuffer** only for multi-threading  
- String is immutable → slower for changes  




# Escape Sequences (Java)

Escape sequences are special characters used inside strings.

---

## Common Escape Sequences

| Escape | Meaning           | Example Output        |
|--------|------------------|----------------------|
| \"     | Double quote     | "hello"              |
| \'     | Single quote     | 'a'                  |
| \n     | New line         | Moves to next line   |
| \t     | Tab              | Adds space (tab)     |
| \\     | Backslash        | \                    |
| \r     | Carriage return  | Moves cursor to start|
| \b     | Backspace        | Deletes previous char|
| \f     | Form feed        | Page break (rare)    |

---

## Example

System.out.println("Hello\nWorld");

Output:
Hello  
World

---

System.out.println("Name:\tAfzal");

Output:
Name:   Afzal

---

System.out.println("He said \"Hello\"");

Output:
He said "Hello"

---

System.out.println("Path: C:\\Users\\Afzal");

Output:
Path: C:\Users\Afzal

---

## Important Notes

- Used inside **String literals**
- Start with **backslash ( \ )**
- Helps format output properly

---

## Quick Memory Tip

- \n → New line  
- \t → Tab  
- \\ → Backslash  