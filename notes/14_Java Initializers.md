# Java Initializers

---

## 🔹 Static Initializer (Static Block)

Used to initialize **static variables**.

### Key Points
- Runs **only once**
- Executes when class is **loaded**
- Used for complex/static setup

---

### Example

import java.util.HashMap;

class Demo {
    static HashMap<String, String> map = new HashMap<>();

    static {
        map.put("John", "111-222-3333");
        map.put("Anita", "222-333-4444");
    }
}

---

### When to Use?
- Static configuration
- Database setup
- Loading constants

---

## 🔹 Instance Initializer (Non-static block)

Used to initialize **instance variables**

### Key Points
- Runs **every time object is created**
- Executes **before constructor**
- Can have multiple blocks (executed in order)

---

### Example

class Demo {
    int x;

    {
        x = 10;
        System.out.println("Instance initializer");
    }

    Demo() {
        System.out.println("Constructor");
    }
}

---

### Output

Instance initializer  
Constructor

---

## 🔹 Execution Order

1. Static block (only once)
2. Instance initializer
3. Constructor

---

## 🔥 Summary

| Type | Runs When | Use Case |
|------|----------|---------|
| Static Initializer | Class load | Static data setup |
| Instance Initializer | Object creation | Shared constructor logic |

---

## ⚠️ Important Notes

- Static block → only for static variables
- Instance block → runs before constructor
- Useful when multiple constructors share same logic

---

## 💡 Simple Trick

- static → class level → runs once  
- instance → object level → runs every time  


# Final Variable in Java

---

## 🔹 What is `final`?

- `final` means **constant (cannot change)**
- Once assigned → value **cannot be reassigned**

---

## 🔹 Types of Final Variables

### 1. Primitive Variables

- Value is constant

```java
final int x = 10;
x = 20; // ❌ ERROR


private static int idInitializer = 1000;
private final int id;
private String name;
private String gender = "male";

public Student(String name, String gender) {
    this.name = name;
    this.gender = gender;

    id = ++idInitializer;  // ✅ Assign once
}




# Final & Constant Variables (Java)

---

## 🔹 1. Constant Variables

A variable is considered a **compile-time constant** if:

✔ declared as `final`  
✔ type is **primitive or String**  
✔ initialized **at declaration**  
✔ value is a **compile-time constant expression**

---

### Example

```java
public static final double PI = 3.14159;
public static final int MAX = 100;