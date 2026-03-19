# Java Math Class (java.lang.Math)

Provides methods for mathematical operations.

---

## 🔹 Basic Methods

| Method | Description | Example |
|--------|------------|--------|
| Math.abs(x) | Absolute value | Math.abs(-5) → 5 |
| Math.max(a, b) | Maximum value | Math.max(10, 20) → 20 |
| Math.min(a, b) | Minimum value | Math.min(10, 20) → 10 |

---

## 🔹 Power & Roots

| Method | Description | Example |
|--------|------------|--------|
| Math.pow(a, b) | a^b | Math.pow(2, 3) → 8.0 |
| Math.sqrt(x) | Square root | Math.sqrt(25) → 5.0 |
| Math.cbrt(x) | Cube root | Math.cbrt(27) → 3.0 |

---

## 🔹 Rounding Methods

| Method | Description | Example |
|--------|------------|--------|
| Math.round(x) | Nearest integer | Math.round(4.6) → 5 |
| Math.ceil(x) | Round up | Math.ceil(4.2) → 5.0 |
| Math.floor(x) | Round down | Math.floor(4.9) → 4.0 |

---

## 🔹 Random

| Method | Description | Example |
|--------|------------|--------|
| Math.random() | 0.0 ≤ value < 1.0 | Math.random() → 0.73 |

👉 Range example:
(int)(Math.random() * 100) → 0 to 99

---

## 🔹 Logarithmic

| Method | Description | Example |
|--------|------------|--------|
| Math.log(x) | Natural log (ln) | Math.log(10) |
| Math.log10(x) | Log base 10 | Math.log10(100) → 2 |

---

## 🔹 Trigonometric

| Method | Description |
|--------|------------|
| Math.sin(x) | Sine |
| Math.cos(x) | Cosine |
| Math.tan(x) | Tangent |
| Math.asin(x) | Arc sine |
| Math.acos(x) | Arc cosine |
| Math.atan(x) | Arc tangent |

👉 NOTE: Input is in **radians**

---

## 🔹 Angle Conversion

| Method | Description |
|--------|------------|
| Math.toRadians(deg) | Degrees → radians |
| Math.toDegrees(rad) | Radians → degrees |

---

## 🔹 Exponential

| Method | Description | Example |
|--------|------------|--------|
| Math.exp(x) | e^x | Math.exp(1) → 2.718 |

---

## 🔹 Constants

| Constant | Value |
|----------|------|
| Math.PI | 3.141592653589793 |
| Math.E | 2.718281828459045 |

---

## 🔹 Example Program

```java
public class MathDemo {
    public static void main(String[] args) {
        System.out.println(Math.abs(-10));
        System.out.println(Math.max(5, 9));
        System.out.println(Math.pow(2, 3));
        System.out.println(Math.sqrt(16));
        System.out.println(Math.ceil(4.2));
        System.out.println(Math.floor(4.9));
        System.out.println(Math.round(4.6));
        System.out.println(Math.random());
    }
}