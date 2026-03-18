# Control Flow Statements

**Definition:**  
Control flow statements control the **execution order** of code.

---

## if Statement

Used to execute code based on condition:

if(condition) {
    // code
}

---

## if-else Statement

if(condition) {
    // true block
} else {
    // false block
}

---

## switch Statement

Used for multiple conditions:

switch(value) {
    case 1:
        // code
        break;
    case 2:
        // code
        break;
    default:
        // code
}

---

## Switch Restrictions

- Works with: int, char, String, enum  
- Case values must be **constant**  
- No duplicate cases  

---

## Switch (Java 14 - Arrow)

switch(value) {
    case 1 -> System.out.println("One");
    case 2 -> System.out.println("Two");
    default -> System.out.println("Other");
}

---

## Switch Expression (Java 14)

int result = switch(value) {
    case 1 -> 10;
    case 2 -> 20;
    default -> 0;
};

---

## Ternary Operator

Short form of if-else:

int result = (condition) ? value1 : value2;

---

## for Loop

for(int i = 0; i < 5; i++) {
    System.out.println(i);
}

---

## Nested for Loop

for(int i = 0; i < 3; i++) {
    for(int j = 0; j < 3; j++) {
        System.out.println(i + " " + j);
    }
}

---

## for-each Loop

int[] arr = {1,2,3};

for(int num : arr) {
    System.out.println(num);
}

---

## while Loop

int i = 0;

while(i < 5) {
    System.out.println(i);
    i++;
}

---

## do-while Loop

int i = 0;

do {
    System.out.println(i);
    i++;
} while(i < 5);

---

## break Statement

Used to exit loop:

for(int i = 0; i < 5; i++) {
    if(i == 3) break;
}

---

## continue Statement

Skips current iteration:

for(int i = 0; i < 5; i++) {
    if(i == 3) continue;
}

---

## Labeled break

outer:
for(int i = 0; i < 3; i++) {
    for(int j = 0; j < 3; j++) {
        break outer;
    }
}

---

## Labeled continue

outer:
for(int i = 0; i < 3; i++) {
    for(int j = 0; j < 3; j++) {
        continue outer;
    }
}

---

## Blocks

{
    int x = 10;
    System.out.println(x);
}

---

## Variable Scope

- Variables exist only inside their block  
- Cannot access outside block  

---

## Recursion

Method calling itself:

int fact(int n) {
    if(n == 0) return 1;
    return n * fact(n - 1);
}

---

## Important Notes

- if → condition check  
- switch → multiple options  
- loops → repetition  
- break → stop  
- continue → skip  
- recursion → self-calling  


## Selector Expression Type Restrictions

**Definition:**  
The value used inside `switch(expression)` must follow specific data types.

---

## Allowed Types

- Integer values (e.g., 7, month, x + y)

Supported types:

- byte  
- short  
- char  
- int  

---

## Also Allowed (Java)

- String  
- enum  

---

## Not Allowed

- long  
- float  
- double  
- boolean  

---

## Example

int x = 2;

switch(x) {
    case 1:
        System.out.println("One");
        break;
    case 2:
        System.out.println("Two");
        break;
}

---

## Important Note

- Expression must return a **compatible type**
- Case values must be **constant values**


## Switch Expression (Java 14 - Arrow Syntax Example)

static String getSeason(int month) {

    String season = null;

    switch (month) {
        case 1, 2, 3 -> season = "Spring";
        case 4, 5, 6 -> season = "Summer";
        case 7, 8, 9 -> season = "Rainy";
        case 10, 11, 12 -> season = "Winter";
        default -> season = "unknown";
    }

    return season;
}

##yield
## Switch Expression with yield (Java 14+)

static String getSeason(int month) {

    return switch (month) {

        case 1, 2, 3 -> { 
            yield "Spring"; 
        }

        case 4, 5, 6 -> { 
            yield "Summer"; 
        }

        case 7, 8, 9 -> { 
            yield "Rainy"; 
        }

        case 10, 11, 12 -> { 
            yield "Winter"; 
        }

        default -> throw new IllegalArgumentException("unknown");
    };
}



## Ternary as Expression Statement

**Rule:**  
Ternary operator **cannot be used alone as a statement**.

---

## Invalid Usage ❌

(boolean-expression) ? true-expr : false-expr;

---

### Example (Invalid)

a > b ? a : b;   // ❌ invalid (no assignment or usage)

---

## Valid Usage ✅

Ternary must be used in:

### 1. Assignment

int max = (a > b) ? a : b;

---

### 2. Return Statement

return (a > b) ? a : b;

---

### 3. Method Argument

System.out.println((a > b) ? a : b);

---

## Key Point

- Ternary is an **expression**, not a standalone statement  
- It must **produce a value that is used somewhere**


## for Statement (Iteration)

**Definition:**  
Used to repeat a block of code a fixed number of times.

---

## Basic Syntax

for (initialization; condition; update) {
    // code
}

---

## Example

int[] iArray = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};

for (int i = 0; i < iArray.length; i++) {
    System.out.println(iArray[i]);
}

---

## Iteration Example

Iteration 1:  
i = 0 → 0 < 10 → print 0  

---

## for-each Loop (Enhanced for)

**Definition:**  
Simpler way to iterate over arrays or collections.

---

## Syntax

for (datatype variable : collection) {
    // code
}

---

## Example

int[] iArray = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};

for (int i : iArray) {
    System.out.print(i + " ");
}

---

## Key Differences

| for loop | for-each loop |
|---------|--------------|
| Uses index (i) | No index |
| Can modify elements | Read-only (usually) |
| More control | Simpler syntax |

---

## Important Notes

- for → best when index is needed  
- for-each → best for simple traversal  