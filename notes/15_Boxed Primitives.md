# Boxed Primitives (Wrapper Classes in Java)

---

## 🔹 1. What are Boxed Primitives?

👉 Java provides **wrapper classes** for primitive types  
👉 They allow primitives to be treated as **objects**

---

## 🔹 Primitive → Wrapper Mapping

| Primitive | Wrapper Class |
|----------|--------------|
| int      | Integer      |
| long     | Long         |
| byte     | Byte         |
| short    | Short        |
| float    | Float        |
| double   | Double       |
| boolean  | Boolean      |
| char     | Character    |

---

## 🔹 2. Why Wrapper Classes?

✔ Required for:
- Collections (`ArrayList`, `HashMap`)
- Generics
- Object-based operations

```java
ArrayList<Integer> list = new ArrayList<>();





# Autoboxing & Unboxing in Java

🔹 What is Autoboxing?  
👉 Automatic conversion: primitive → wrapper object  

Example:

```java
Integer boxed = 25;   // int → Integer (autoboxing)
```

👉 Internally:

```java
Integer boxed = Integer.valueOf(25);
```

---

🔹 What is Unboxing?  
👉 Automatic conversion: wrapper object → primitive  

Example:

```java
Integer boxed = 25;
int value = boxed;   // Integer → int (unboxing)
```

👉 Internally:

```java
int value = boxed.intValue();
```

---

🔹 Full Example

```java
Integer boxed = 25;          // autoboxing
int j = boxed;               // auto-unboxing

Integer obj = new Integer(25);  // ❌ deprecated (avoid)
int x = obj.intValue();         // manual unboxing
```

---

🔹 Key Points

- Autoboxing → primitive → object  
- Unboxing → object → primitive  
- Java performs conversion automatically  
- Avoid using `new Integer()`  
- Prefer `Integer.valueOf()`  

---

🔹 Important Warning

```java
Integer x = null;
int y = x;   // ❌ NullPointerException
```

---

🔹 Performance Note

```java
Integer sum = 0;

for (int i = 0; i < 1000; i++) {
    sum += i;   // ❌ boxing + unboxing repeatedly
}
```

👉 Better:

```java
int sum = 0;   // ✅ faster
```

---

🔹 Summary

- Autoboxing = primitive → object  
- Unboxing = object → primitive  
- Use wrappers for collections & generics  
- Use primitives for better performance  