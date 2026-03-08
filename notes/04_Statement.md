## Statement Types

In Java, statements can be grouped into several categories depending on what they do in a program.

---

### 1. Declaration Statements

A declaration statement is used to **declare a variable and optionally assign it a value**.

Example:

```java
int count = 25;
```

Explanation:

| Part | Meaning |
|-----|--------|
| `int` | Data type |
| `count` | Variable name |
| `25` | Assigned value |

---

### 2. Expression Statements

Expression statements perform an **operation or action** in the program.

Common types include:

#### Assignment Statement

```java
count = 25;
```

Changes the value stored in the variable.

---

#### Method Invocation Statement

```java
getCount();
```

Calls a method.

---

#### Increment Statement

```java
count++;
```

Increases the value of `count` by **1**.

Equivalent to:

```java
count = count + 1;
```

---

> [!IMPORTANT]
> Expression statements **cannot appear directly at the class level**.  
> They must be placed **inside a method, constructor, or initialization block**.

Example of incorrect code:

```java
class Test {

    int count = 25;

    count++;   // ❌ Not allowed at class level

}
```

Correct usage:

```java
class Test {

    int count = 25;

    void increase() {
        count++;   // ✅ Allowed inside a method
    }

}
```

---

### 3. Control Flow Statements

Control flow statements determine **how the program executes instructions**.

Example:

```java
if (count < 100) {
    System.out.println("Count is less than 100");
}
```

Control flow statements include:

- `if`
- `if-else`
- `switch`
- `for`
- `while`
- `do-while`
- `break`
- `continue`

---

### Summary

| Statement Type | Example | Purpose |
|---------------|--------|--------|
| Declaration | `int count = 25;` | Declare variables |
| Expression | `count++;` | Perform operations |
| Method invocation | `getCount();` | Call methods |
| Control flow | `if (count < 100)` | Control execution |

---