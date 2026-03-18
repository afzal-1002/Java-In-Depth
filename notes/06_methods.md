# Methods

**Definition:**  
A method is a block of code that performs a specific task and can be reused.

- **Reusable** – can be called multiple times  
- **Modular** – helps organize code  
- **Readable** – makes code easier to understand  

---

## Syntax

return Type methodName(type param1, type param2, ...) {
    // code
    return value;
}

---

## Example

int add(int a, int b) {
    return a + b;
}

---

## Calling a Method

int result = add(2, 3);

---

## Types of Methods

**1. Method with return value**
int sum(int a, int b) {
    return a + b;
}

**2. Method without return value (void)**
void printHello() {
    System.out.println("Hello");
}

---

## Parameters

- **Parameters** → variables in method definition  
- **Arguments** → values passed when calling method (method invocation) 

Example:

int add(int a, int b) {   // parameters
    return a + b;
}

add(5, 3);  // arguments

---

## Method with No Parameters

void greet() {
    System.out.println("Hi");
}

---

## Method Overloading

int add(int a, int b) {
    return a + b;
}

int add(int a, int b, int c) {
    return a + b + c;
}

---

## Important Points

- Method must have a **return type**
- Use **void** if nothing is returned  
- Method name should be **meaningful**  
- Execution starts from **main() method**  

---

## Main Method

public static void main(String[] args) {
    System.out.println("Program starts here");
}


# Method Types

## Instance Methods

**Definition:**  
Methods that belong to an **object (instance)** of a class.

- **Object-level methods**
- Require an object to call
- Can access **instance variables and methods**

**Invocation:**
objectReference.methodName();

**Example:**
class Student {
    int age = 20;

    void display() {
        System.out.println(age);
    }
}

Student s = new Student();
s.display();

---

## Static Methods

**Definition:**  
Methods that belong to the **class**, not to any object.

- Use keyword **static**
- **Class-level methods**
- Do NOT require object
- Cannot directly access instance variables/methods

**Invocation:**
ClassName.methodName();

**Example:**
class MathUtils {
    static int add(int a, int b) {
        return a + b;
    }
}

int result = MathUtils.add(2, 3);

---

## Key Difference

| Feature           | Instance Method      | Static Method         |
|-------------------|----------------------|-----------------------|
| Belongs to        | Object               | Class                 |
| Requires Object   | Yes                  | No                    |
| Access Instance   | Yes                  | No (directly)         |
| Access Static     | Yes                  | Yes                   |

---

## Important Notes

- Instance methods → need object  
- Static methods → use class name  
- Static cannot access instance data directly  
- Instance can access both static and instance  




# Memory & Data Passing in Java

---

## Passing Data

- Identical to **variable assignment**
- method parameter = method argument  

Example:

void updateId(int newId) {
    newId = 1001;
}

int id = 1000;
updateId(id);

Equivalent to:

int id = 1000;
int newId = id;
newId = 1001;

---

## Primitives in Memory

int id = 1000;

- id → logical name, memory address, value  
- Stores **actual value directly in memory**

---

## Object References in Memory

Student s = new Student();

- s stores **reference (address)**  
- Actual object is stored in **heap memory**  
- Variable points to memory location  

---

## Pass by Value: Primitives

void updateId(int newId) {
    newId = 1001;
}

int id = 1000;
updateId(id);

- A **copy of value** is passed  
- Original value is NOT changed  

---

## Pass by Value: Object References

void updateId(Student s1) {
    s1.id = 1001;
}

Student s = new Student();
s.id = 1000;

updateId(s);

- A **copy of reference** is passed  
- Both point to SAME object  
- Changes affect original object  

---

## Key Concept

- Java is ALWAYS **pass by value**
- For primitives → value is copied  
- For objects → reference is copied  

---

## Important Difference

| Type        | What is Passed        | Can Change Original? |
|------------|----------------------|---------------------|
| Primitive   | Value                | ❌ No               |
| Object      | Reference (copy)     | ✅ Yes              |

---

## Easy Memory Trick

- Primitive → **value copied**  
- Object → **reference copied → same object modified**  




# Method Overloading

**Definition:**  
Same method name, but **different parameter lists**.

- MUST change **parameter list**
- Improves **readability**
- Supports **compile-time polymorphism**

---

## Rules

- Method name must be the **same**
- Parameters must be **different**:
  - Different number of parameters  
  - Different data types  
  - Different order of parameters  
- Return type alone is NOT enough

---

## Valid Examples
void updateProfile(int newId) {}
void updateProfile(int newId, char gender) {}
void updateProfile(char gender, int newId) {}
void updateProfile(short newId) {}

---

## Invalid Example

int update(int a) { return a; }

double update(int a) { return a; }   // ❌ Not allowed (only return type different)

---

## Example

int add(int a, int b) {
    return a + b;
}

int add(int a, int b, int c) {
    return a + b + c;
}

---

## Important Notes

- Decided at **compile time**
- Also called **static polymorphism**
- Helps avoid multiple method names  


# Varargs (Variable Arguments)

**Definition:**  
Allows a method to take a **variable number of arguments**.

- Before Java 5 → fixed number of arguments  
- Varargs → variable-length arguments  
- Last parameter can take **multiple values**  
- Can be the **only parameter**

---

## Syntax

- Use **three dots (...)** after data type

Example:

void foo(boolean flag, int... items) {
    // items behaves like an array
}

---

## Invocation

**Using Array:**

foo(true, new int[]{1, 2, 3});

**Using Comma-Separated Values:**

foo(true, 1, 2, 3);

---

## Example

int sum(int... numbers) {
    int total = 0;
    for(int n : numbers) {
        total += n;
    }
    return total;
}

sum(1, 2);        // 3
sum(1, 2, 3, 4);  // 10

---

## Important Rules

- Varargs must be the **last parameter**
- Only **one varargs** parameter allowed
- Internally treated as an **array**

---

## Key Point

int... nums  → behaves like  → int[] nums

## Why Varargs?

- Can’t we use:
  foo(boolean flag, int[] items)?

- Varargs provides **simpler & flexible invocation**

Examples:

foo(true, 1, 2, 3);

foo(true);  
// no need to write:
// foo(true, null)
// foo(true, new int[]{})

foo(true, veryLargeArray);

---

## Real Example

printf(String format, Object... args)

System.out.printf("DOB: %d/%d/%d", 1, 1, 1978);
// Output: DOB: 1/1/1978