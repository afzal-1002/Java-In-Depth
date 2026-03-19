# Accessing Classes & Import

---

## Accessing Classes

- Same package → **direct access**
- Different package:
  - Use **import**
  - Or use **fully-qualified class name (rare)**

---

## import Statement

import java.util.ArrayList;

class FooClass {
    void foo() {
        ArrayList list = new ArrayList();
    }
}

---

## Importing Single vs Multiple Classes

### Import Single Class

- Explicit import (Single-Type-Import)

import java.util.ArrayList;

---

### Import Multiple Classes

- Multiple explicit imports

import java.util.ArrayList;
import java.util.Date;

---

- Using wildcard (*)

import java.util.*;

---

## * Import

- Imports **all classes in a package**

import java.util.*;

---

## Important Note

- `*` does NOT import sub-packages  
- Only imports classes in that package  

---

## Problem with * Import ❌

import java.util.*;
import java.sql.*;

Date date;   // ❌ ambiguous (compiler error)

---

## Why Error?

- Both packages contain `Date` class:
  - java.util.Date  
  - java.sql.Date  

---

## Better Practice ✅

Use explicit import for clarity:

import java.util.Date;
import java.sql.*;

Date date;           // from util
java.sql.Date date2; // from sql

---

## Fully Qualified Class Name

Alternative to import:

java.util.ArrayList list = new java.util.ArrayList();

---

## When to Use Fully Qualified Name

- When two classes have **same name**
- Avoid ambiguity

---

## Solution 1

Use one explicit import:

import java.util.Date;
import java.sql.*;

Date date;
java.sql.Date date2;

---

## Solution 2

Use fully-qualified names:

import java.util.*;
import java.sql.*;

java.util.Date date;
java.sql.Date date2;

---

## Key Points

- Same package → direct access  
- Different package → import required  
- Avoid `*` when class name conflicts  
- Prefer explicit import for clarity  

# Package Statement

**Definition:**  
A package is used to **group related classes** together.

---

## Syntax

package package-name;

Example:

package com.semanticsquare.basics;

---

## Important Rule

- Must be the **first statement** in the file  
- Comes **before import statements**

---

## Example

package com.semanticsquare.basics;

import java.util.ArrayList;

class BasicsDemo {
    // code
}

---

# Effect of Creating Package

- Package name becomes part of **class name**

---

## Example

❌ Wrong:

java BasicsDemo  

---

## Correct:

java com.semanticsquare.basics.BasicsDemo  

---

## Key Points

- Package helps in **organization**
- Avoids **naming conflicts**
- Required for **large applications**