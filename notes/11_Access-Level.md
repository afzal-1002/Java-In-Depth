# Access Modifiers

**Definition:**  
Access modifiers provide **restrictions** on accessing classes (interfaces) and their members.

---

## Purpose

- Control visibility of classes and variables  
- Help build **well-designed software**

---

# Accessibility for Classes / Interfaces

- Inside same package → default access  
- Inside & outside package → **public**

---

## Example

public class BasicsDemo {
    // code
}

---

# Accessibility for Class Members

## 1. private

- Accessible **only inside the class**

private int id = 4;

---

## 2. default (no modifier)

- Accessible **only inside the same package**

int id = 4;

---

## 3. protected

- Accessible:
  - Inside same package  
  - Outside package (only via subclass)

protected int id = 4;

---

## 4. public

- Accessible **everywhere**

public int id = 4;

---

# Summary Table

| Modifier  | Same Class | Same Package | Subclass (Other Package) | Other Package |
|-----------|------------|--------------|--------------------------|---------------|
| private   | 	✅      	| 	❌         | 	      ❌            	| 		❌      |
| default   | 	✅       | 	✅         | 	      ❌             | 		❌      |
| protected | 	✅       | 	✅         | 	      ✅             | 		❌      |
| public    | 	✅       | 	✅         | 	      ✅             | 		✅      |

---

## Key Points

- `private` → most restricted  
- `public` → most accessible  
- `protected` → useful for inheritance  
- default → package-level access  