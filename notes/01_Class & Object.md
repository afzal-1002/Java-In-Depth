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
Every Variable has a data type (Java is static Type Language) 
it holds the value ();
int num = 45;
String name = " Muhammad" 
Type is fixed: When we declare the varible we define the type can not be changed.

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