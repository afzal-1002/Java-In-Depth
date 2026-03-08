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


# Variables
## 1. Variables :  <Type> <name> [=literal or expression]
Every Variable has a data type (Java is static Type Language)  it holds the value;
Type is fixed: When we declare the varible we define the type can not be changed.

int num = 45;
String name = " Muhammad" 
int num = 45_5; 


String name = "Muhammad" | Object Reference
String name = new String("Muhammad") | Object Reference

public Class Student{
	int id = 100;
	int nextId = id +1;

	String name;
	name = "Afzal"; => not possible 


	 void comput()
	 {
		system.out.println(id);
		system.out.println(nextId);
	 }

}

## 2. Primitive Types

Java has **8 primitive data types**:

| Type     | Size (Bytes) | Size (Bits) 	| Example                     	| Description 						|
|----------|--------------|-------------	|-----------------------------	|-------------						|
| byte     | 1 byte       | 8 bits      	| `byte a = 10;`              	| Small integer 					| 
| short    | 2 bytes      | 16 bits     	| `short b = 1000;`           	| Short integer 					|
| int      | 4 bytes      | 32 bits     	| `int c = 100000;`           	| Most common integer type 			|
| long     | 8 bytes      | 64 bits     	| `long d = 10000000000L;`    	| Large integer 					|
| float    | 4 bytes      | 32 bits     	| `float e = 5.5f;`           	| Decimal number (single precision) |
| double   | 8 bytes      | 64 bits     	| `double f = 10.99;`         	| Decimal number (double precision) |
| char     | 2 bytes      | 16 bits     	| `char g = 'A';`             	| Single character (Unicode) 		|
| boolean  | JVM dependent| JVM dependent 	| `boolean h = true;`        	| True or false value 				|

| Type    | Size (Bytes)  | Size (Bits)   | Value Range         | Example                  |
| ------- | ------------- | ------------- | ------------------- | ------------------------ |
| byte    | 1 byte        | 8 bits        | **-2⁷ to 2⁷ − 1**   | `byte a = 10;`           |
| short   | 2 bytes       | 16 bits       | **-2¹⁵ to 2¹⁵ − 1** | `short b = 1000;`        |
| int     | 4 bytes       | 32 bits       | **-2³¹ to 2³¹ − 1** | `int c = 100000;`        |
| long    | 8 bytes       | 64 bits       | **-2⁶³ to 2⁶³ − 1** | `long d = 10000000000L;` |
| float   | 4 bytes       | 32 bits       | **≈ ±2¹²⁸**         | `float e = 5.5f;`        |
| double  | 8 bytes       | 64 bits       | **≈ ±2¹⁰²⁴**        | `double f = 10.99;`      |
| char    | 2 bytes       | 16 bits       | **0 to 2¹⁶ − 1**    | `char g = 'A';`          |
| boolean | JVM dependent | JVM dependent | **true / false**    | `boolean h = true;`      |


Range example
byte: -128 → 127
Because: 2^8 = 256 values

Byte.MAX_VALUE;
Byte.MIN_VALUE;

long num = 5465454L;

Hexa formate: 
	MAX_VALUE = 0x7ffffff;
	int intHex= 0x0041 // 16 power 0 + 1 + 16 poewer 1 * 4
	long longHex = 0x004L;

Octal: 
	int intOctal = 0101;

Binary: 
	int intBinary = 0b01000001; => 65
	So Java reads it as: 01000001
	| Bit | Value   |
	| --- | ------- |
	| 1   | 2⁰ = 1  |
	| 0   | 2¹ = 0  |
	| 0   | 2² = 0  |
	| 0   | 2³ = 0  |
	| 0   | 2⁴ = 0  |
	| 0   | 2⁵ = 0  |
	| 1   | 2⁶ = 64 |
	| 0   | 2⁷ = 0  |

	64 + 1 = 65
	0b0100_0001 = 65

	char c = 0b0100_0001;
	System.out.println(c); => A

	int x = 0b0100_0001;
	System.out.println(x); => 65


** Floating point **
| Type       | Bit depth | Value range         | Default | Precision            |
| ---------- | --------- | ------------------- | ------- | -------------------- |
| **float**  | 32 bits   | -3.4E38 to 3.4E38   | 0.0f    | 6–7 decimal digits   |
| **double** | 64 bits   | -1.7E308 to 1.7E308 | 0.0d    | 15–16 decimal digits |

float:
	Uses 32 bits
	Stores numbers roughly between
	-3.4 × 10³⁸ and 3.4 × 10³⁸
	Precision: 6–7 digits
	float x = 3.14f;

double:
	Uses 64 bits
	Stores numbers roughly between
	-1.7 × 10³⁰⁸ and 1.7 × 10³⁰⁸
	Precision: 15–16 digits
	double y = 3.14159265358979;

By Default:
	it would be a double:
	doube num = 4.88;
	double num = 4.88d;
	float gpa = 2.53f;

BigDecimal: (import java.math.BigDecimal;)
		BigDecimal is a Java class used to store very precise decimal numbers.

		When dealing with money use BigDecimal:
		Avoid Float and Double when exact answer are require
		BigDecimal one =  new BigDecimal("0.1");
		BigDecimal second =  new BigDecimal("0.2");
		System.out.println(one.add(secnd));

Methods:
		add subtract multiply divide compaterTo
		int x = 10;
		BigDecimal bd = BigDecimal.valueOf(x);

Get user input and convert to BigDecimal:
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter number:");
		BigDecimal number = new BigDecimal(sc.nextLine());
		System.out.println(number);

Create an Array of BigDecimal:
		import java.math.BigDecimal;

		BigDecimal[] numbers = new BigDecimal[3];

		numbers[0] = new BigDecimal("10.5");
		numbers[1] = new BigDecimal("20.7");
		numbers[2] = new BigDecimal("30.9");

Create a List of BigDecimal:
		import java.math.BigDecimal;
		import java.util.ArrayList;
		import java.util.List;

		List<BigDecimal> numbers = new ArrayList<>();

		numbers.add(new BigDecimal("10.5"));
		numbers.add(new BigDecimal("20.7"));
		numbers.add(new BigDecimal("30.9"));

Stream on List of BigDecimal:
		numbers.stream().forEach(System.out::println);

		Filter values greater than 20
		numbers.stream().filter(n -> n.compareTo(new BigDecimal("20"))> 0).forEach(System.out::println);

Most important BigDecimal operations:
		| Operation | Method           |
		| --------- | ---------------- |
		| add       | `a.add(b)`       |
		| subtract  | `a.subtract(b)`  |
		| multiply  | `a.multiply(b)`  |
		| divide    | `a.divide(b)`    |
		| compare   | `a.compareTo(b)` |
