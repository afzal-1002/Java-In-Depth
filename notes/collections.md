📘 Table of Contents

Variables

Object References

Primitive Data Types

Number Literals

Floating Point Numbers

BigDecimal

Character Type

Boolean Type

Variable Scope

1. Variables

A variable stores a value in memory.

Java is a statically typed language, meaning:

Every variable must have a type

The type cannot change after declaration

Syntax
<Type> <name> = <literal | expression>;
Examples
int num = 45;
String name = "Muhammad";

Numeric literals can include underscores for readability.

int population = 1_000_000;

🎯 Important

Java variables must always be declared with a type before use.

2. Object References

Objects in Java are stored using references.

String name = "Muhammad";
String name2 = new String("Muhammad");

Both variables store references to String objects.

Example Class
public class Student {

    int id = 100;
    int nextId = id + 1;

    String name;

    void compute() {
        System.out.println(id);
        System.out.println(nextId);
    }
}

🎯 Important

You cannot assign values directly in the class body like this:

String name;
name = "Afzal"; // ❌ Not allowed outside methods or constructors

Assignments must occur inside:

constructors

methods

initializer blocks

3. Primitive Data Types

Java has 8 primitive data types.

Type	Size	Bits	Example	Description
byte	1 byte	8	byte a = 10;	Small integer
short	2 bytes	16	short b = 1000;	Short integer
int	4 bytes	32	int c = 100000;	Most common integer
long	8 bytes	64	long d = 10000000000L;	Large integer
float	4 bytes	32	float e = 5.5f;	Decimal number
double	8 bytes	64	double f = 10.99;	Decimal number
char	2 bytes	16	char g = 'A';	Character
boolean	JVM dependent	JVM dependent	boolean h = true;	True / False
Primitive Type Range
Type	Range
byte	-2⁷ → 2⁷ − 1
short	-2¹⁵ → 2¹⁵ − 1
int	-2³¹ → 2³¹ − 1
long	-2⁶³ → 2⁶³ − 1
float	≈ ±2¹²⁸
double	≈ ±2¹⁰²⁴
char	0 → 65535

Example:

Byte.MAX_VALUE
Byte.MIN_VALUE

🎯 Important

int is the most commonly used integer type in Java.

4. Number Literals
Long Literal
long num = 5465454L;
Hexadecimal
int intHex = 0x0041;
long longHex = 0x004L;

Example calculation:

0x0041 = (4 × 16¹) + (1 × 16⁰)
Octal
int intOctal = 0101;
Binary
int intBinary = 0b01000001;

Binary breakdown:

Bit	Value
1	2⁰ = 1
0	2¹ = 0
0	2² = 0
0	2³ = 0
0	2⁴ = 0
0	2⁵ = 0
1	2⁶ = 64
0	2⁷ = 0
64 + 1 = 65
char c = 0b0100_0001;
System.out.println(c); // A

int x = 0b0100_0001;
System.out.println(x); // 65
5. Floating Point Numbers
Type	Bits	Range	Default	Precision
float	32	-3.4E38 → 3.4E38	0.0f	6–7 digits
double	64	-1.7E308 → 1.7E308	0.0d	15–16 digits
Float
float x = 3.14f;

32 bits

Precision: 6–7 digits

Double
double y = 3.14159265358979;

64 bits

Precision: 15–16 digits

🎯 Important

Decimal numbers are double by default.

double num = 4.88;
float gpa = 2.53f;
6. BigDecimal (High Precision Numbers)
import java.math.BigDecimal;

BigDecimal is used when exact precision is required.

Example:

BigDecimal one = new BigDecimal("0.1");
BigDecimal two = new BigDecimal("0.2");

System.out.println(one.add(two));

🎯 Important

Always create BigDecimal from String.

new BigDecimal("0.1") // correct

Avoid:

new BigDecimal(0.1) // incorrect precision
BigDecimal Operations
Operation	Method
add	a.add(b)
subtract	a.subtract(b)
multiply	a.multiply(b)
divide	a.divide(b)
compare	a.compareTo(b)
BigDecimal List Example
List<BigDecimal> numbers = new ArrayList<>();

numbers.add(new BigDecimal("10.5"));
numbers.add(new BigDecimal("20.7"));
numbers.add(new BigDecimal("30.9"));
Stream Example
numbers.stream().forEach(System.out::println);

Filter example:

numbers.stream()
       .filter(n -> n.compareTo(new BigDecimal("20")) > 0)
       .forEach(System.out::println);
7. Character Type
char letter = 'A';
char number = '5';
char symbol = '@';
Type	Bits
char	16 bits

Range:

0 → 65535
ASCII / Unicode Example
char c = 65;
System.out.println(c); // A
UTF-16 Encoding

Java stores characters using UTF-16.

Example:

'B'
Unicode → U+0042
Binary → 00000000 01000010

Unicode representation:

'\u0042'
MIN_VALUE = '\u0000'
MAX_VALUE = '\uFFFF'
Ways to Initialize char
char c = 'A';          // literal
char c = 65;           // ASCII
char c = '\u0041';     // Unicode
char c = (char)66;     // casting

From String:

String s = "Hello";
char c = s.charAt(0);

From user input:

Scanner sc = new Scanner(System.in);
char c = sc.next().charAt(0);
8. Boolean Type
boolean isLoggedIn = true;
boolean isAdmin = false;

Boolean stores true or false.

Final Boolean

final means the value cannot change after assignment.

final boolean DEBUG_MODE = true;
final boolean IS_PRODUCTION = false;

🎯 Important

A final variable can only be assigned once.

9. Variable Scope

Java has three types of variables.

1. Instance Variables

Belong to an object.

class Student {
    int age;
}

Example:

Student s1 = new Student();
Student s2 = new Student();

Each object has its own copy.

2. Static Variables

Belong to the class itself.

class Student {
    static int count;
}

Usage:

Student.count = 10;

All objects share the same variable.

3. Local Variables

Declared inside methods.

class Test {

    void show() {

        int x = 10;

        System.out.println(x);
    }
}

Scope: only inside the method.

Variable Scope Summary
Type	Location	Scope	Default Value
Instance	inside class	object	yes
Static	inside class	class	yes
Local	inside method	method	no
Example
class Example {

    int age;           // instance variable
    static int count;  // static variable

    void show() {

        int x = 10;    // local variable

        System.out.println(x);
    }
}
Memory Trick
Local    → inside method
Instance → inside object
Static   → inside class