# Naming Rules for Classes

## 1. First Character
The first character of a class name must be:

- A **letter (A–Z, a–z)**
- An **underscore (_)**  
- A **dollar sign ($)**

## 2. Remaining Characters
The remaining characters can be:
+ It can include letters (a-z, A-Z), digits (0-9), the underscore character (_), and the dollar sign ($).
+ It cannot begin with a digit. Subsequent characters can include a digit.
+ It cannot be a reserved keyword in Java (e.g., class, interface, public, static, etc.).

- Letters
- Numbers
- Underscore `_`
- Dollar sign `$`

## 3. Reserved Keywords
Class names **cannot use Java reserved keywords**.

Example of invalid class names:
int byte short double and so on


## 4. Java is a case sensitive
int num = 5;
int Num = 5;

void foo();
void Foo();

are two Methods and variables:


# Java Variables & Data Types

A structured guide to **Java variables, primitive types, number systems, and variable scope**.

---

# 📘 Table of Contents

- [Variables](#variables)
- [Object References](#object-references)
- [Primitive Data Types](#primitive-data-types)
- [Number Literals](#number-literals)
- [Floating Point Numbers](#floating-point-numbers)
- [BigDecimal (High Precision Numbers)](#bigdecimal-high-precision-numbers)
- [Character Type](#character-type)
- [Boolean Type](#boolean-type)
- [Variable Scope](#variable-scope)

---

# Variables

A **variable** stores a value in memory.

Java is a **statically typed language**, meaning:

- Every variable must have a **type**
- The **type cannot change after declaration**

## Syntax

```java
<Type> <name> = <literal | expression>;
```

## Examples

```java
int num = 45;
String name = "Muhammad";
```

Numeric literals can include underscores for readability:

```java
int population = 1_000_000;
```

---

> 🎯 **Important**  
> Java variables must always be declared **with a type before use**.

---

# Object References

Objects in Java are stored using **references**.

```java
String name = "Muhammad";
String name2 = new String("Muhammad");
```

Both variables store **references to String objects**.

---

## Example Class

```java
public class Student {

	int id = 100;
	int nextId = id + 1;

	String name;

	void compute() {
		System.out.println(id);
		System.out.println(nextId);
	}

}
```

---

> 🎯 **Important**

You cannot assign values directly in the class body like this:

```java
String name;
name = "Afzal"; // ❌ Not allowed outside methods or constructors
```

Assignments must occur inside:

- constructors  
- methods  
- initializer blocks  

---

# Primitive Data Types

Java has **8 primitive data types**.

| Type | Size | Bits | Example | Description |
|-----|-----|-----|-----|-----|
| byte | 1 byte | 8 | `byte a = 10;` | Small integer |
| short | 2 bytes | 16 | `short b = 1000;` | Short integer |
| int | 4 bytes | 32 | `int c = 100000;` | Most common integer |
| long | 8 bytes | 64 | `long d = 10000000000L;` | Large integer |
| float | 4 bytes | 32 | `float e = 5.5f;` | Decimal number |
| double | 8 bytes | 64 | `double f = 10.99;` | Decimal number |
| char | 2 bytes | 16 | `char g = 'A';` | Character |
| boolean | JVM dependent | JVM dependent | `boolean h = true;` | True / False |

---

## Primitive Range

| Type | Range |
|-----|-----|
| byte | -2⁷ → 2⁷ − 1 |
| short | -2¹⁵ → 2¹⁵ − 1 |
| int | -2³¹ → 2³¹ − 1 |
| long | -2⁶³ → 2⁶³ − 1 |
| float | ≈ ±2¹²⁸ |
| double | ≈ ±2¹⁰²⁴ |
| char | 0 → 65535 |

Example:

```java
Byte.MAX_VALUE
Byte.MIN_VALUE
```

---

> 🎯 **Important**  
> `int` is the **most commonly used integer type in Java**.

---

# Number Literals

## Long Literal

```java
long num = 5465454L;
```

---

## Hexadecimal (Base 16)

```java
int intHex = 0x0041;
long longHex = 0x004L;
```

Example:

```
0x0041 = (4 × 16¹) + (1 × 16⁰)
```

---

## Octal (Base 8)

```java
int intOctal = 0101;
```

---

## Binary (Base 2)

```java
int intBinary = 0b01000001;
```

Binary conversion:

| Bit | Value |
|----|----|
|1|2⁰ = 1|
|0|2¹ = 0|
|0|2² = 0|
|0|2³ = 0|
|0|2⁴ = 0|
|0|2⁵ = 0|
|1|2⁶ = 64|
|0|2⁷ = 0|

```
64 + 1 = 65
```

Example:

```java
char c = 0b0100_0001;
System.out.println(c); // A

int x = 0b0100_0001;
System.out.println(x); // 65
```

---

# Floating Point Numbers

| Type | Bits | Range | Default | Precision |
|-----|-----|-----|-----|-----|
| float | 32 | -3.4E38 → 3.4E38 | 0.0f | 6–7 digits |
| double | 64 | -1.7E308 → 1.7E308 | 0.0d | 15–16 digits |

---

## Float

```java
float x = 3.14f;
```

- 32 bits
- Precision: 6–7 digits

---

## Double

```java
double y = 3.14159265358979;
```

- 64 bits
- Precision: 15–16 digits

---

> 🎯 **Important**

Decimal numbers are **double by default**.

```java
double num = 4.88;
float gpa = 2.53f;
```

---

# BigDecimal (High Precision Numbers)

```java
import java.math.BigDecimal;
```

`BigDecimal` is used when **exact precision is required** (especially for financial calculations).

Example:

```java
BigDecimal one = new BigDecimal("0.1");
BigDecimal two = new BigDecimal("0.2");

System.out.println(one.add(two));
```

---

> 🎯 **Important**

Always create `BigDecimal` using **String values**.

Correct:

```java
new BigDecimal("0.1");
```

Avoid:

```java
new BigDecimal(0.1);
```

---

## BigDecimal Operations

| Operation | Method |
|-----|-----|
| add | `a.add(b)` |
| subtract | `a.subtract(b)` |
| multiply | `a.multiply(b)` |
| divide | `a.divide(b)` |
| compare | `a.compareTo(b)` |

---

## BigDecimal List Example

```java
List<BigDecimal> numbers = new ArrayList<>();

numbers.add(new BigDecimal("10.5"));
numbers.add(new BigDecimal("20.7"));
numbers.add(new BigDecimal("30.9"));
```

Stream example:

```java
numbers.stream().forEach(System.out::println);
```

Filter example:

```java
numbers.stream()
	   .filter(n -> n.compareTo(new BigDecimal("20")) > 0)
	   .forEach(System.out::println);
```

---

# Character Type

```java
char letter = 'A';
char number = '5';
char symbol = '@';
```

| Type | Bits |
|-----|-----|
| char | 16 bits |

Range:

```
0 → 65535
```

---

## ASCII / Unicode Example

```java
char c = 65;
System.out.println(c); // A
```

---

## UTF-16 Encoding

Java stores characters using **UTF-16 encoding**.

Example:

```
'B'
Unicode → U+0042
Binary → 00000000 01000010
```

Unicode representation:

```java
'\u0042'
```

```
MIN_VALUE = '\u0000'
MAX_VALUE = '\uFFFF'
```

---

## Ways to Initialize char

```java
char c = 'A';
char c = 65;
char c = '\u0041';
char c = (char)66;
```

From String:

```java
String s = "Hello";
char c = s.charAt(0);
```

From user input:

```java
Scanner sc = new Scanner(System.in);
char c = sc.next().charAt(0);
```

---

# Boolean Type

```java
boolean isLoggedIn = true;
boolean isAdmin = false;
```

Boolean stores **true or false values**.

---

## Final Boolean

`final` means the value **cannot change after assignment**.

```java
final boolean DEBUG_MODE = true;
final boolean IS_PRODUCTION = false;
```

---

> 🎯 **Important**

A `final` variable can **only be assigned once**.

---

