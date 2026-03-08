# Object References in Java

In Java, **objects are accessed using references**.

Example:

```java
Student s = new Student();

## 1️⃣ Create a Reference Variable

```
Student s
```

- `Student` → reference type
- `s` → reference variable
- Space is allocated to store a **memory address**

---

## 2️⃣ Create an Object

```
new Student()
```

- Creates a **new object**
- Memory is allocated on the **heap**

---

## What Happens Internally

```
Student s = new Student();
```

Step-by-step:

```
1. Allocate space for reference variable
2. Create new Student object in heap
3. Store object's memory address inside s
```

---

## Visualization

```
Reference Variable                Heap Memory
------------------                ----------------

      s        ─────────────►      Student Object
   (reference)                     { id, name, ... }
```

The variable **does not store the object**.

It stores the **address of the object in memory**.

---

> [!IMPORTANT]
> Java variables of object types **store references, not the actual objects**.

---

# Where Are Objects Stored?

Objects in Java are stored in the **Heap Memory**.

Example:

```java
Student s = new Student();
```

Memory structure:

```
Stack (Reference)          Heap (Object)

     s  ─────────────►      Student Object
                           id
                           name
```

---

## Stack vs Heap

| Memory Area | Stores |
|-------------|--------|
| Stack | Reference variables |
| Heap | Actual objects |

Example:

```
Stack                     Heap
------                    ------

s   ─────────────►        Student Object
                          age = 20
                          name = "Ali"
```

---

> [!NOTE]
> Multiple references can point to the **same object in heap memory**.

Example:

```java
Student s1 = new Student();
Student s2 = s1;
```

Visualization:

```
s1 ──┐
     ├──────► Student Object
s2 ──┘
```

Both variables refer to the **same object**.

---

# Example Program

```java
class Student {

    int id;
    String name;

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.id = 1;
        s.name = "Afzal";

        System.out.println(s.id);
        System.out.println(s.name);

    }

}
```

---

# Summary

| Concept | Description |
|------|------|
| Reference Variable | Stores memory address |
| Object | Stored in heap |
| `new` keyword | Creates object |
| Heap | Stores objects |
| Stack | Stores references |

---

> [!TIP]
> Always remember:  
> **Object variable = reference to object, not the object itself.**

---