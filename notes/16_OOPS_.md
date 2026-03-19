# Object-Oriented Programming (OOP) in Java

## 📚 Table of Contents

- [Inheritance](#inheritance-in-java)
- [Polymorphism](#polymorphism-in-java)
- [Abstraction](#abstraction-in-java)
- [Encapsulation](#encapsulation-in-java)

---

# Inheritance in Java

🔹 What is Inheritance?  
👉 Mechanism where one class acquires properties (fields + methods) of another class  

👉 Promotes:
- Code reuse  
- Better design  
- Hierarchical relationships  

---

🔹 Basic Syntax

    class Parent {
    }

    class Child extends Parent {
    }

---

🔹 Example (Real Structure)

    class User {
        void saveWebLink() {}
        void saveMovie() {}
        void saveBook() {}
        void rateBookmark() {}
        void postAReview() {}
    }

    class Staff extends User {
        void postAReview() {}
    }

    class EmailAdmin extends Staff {
        void handleEmailCampaign() {}
    }

    class Editor extends Staff {
        void approveReview() {}
        void rejectReview() {}
    }

    class ChiefEditor extends Editor {
        void updateHomepage() {}
    }

---

🔹 Key Concepts

- Superclass (Parent) → class being inherited  
- Subclass (Child) → class that inherits  

---

🔹 What Subclasses Can Do

- Inherit members  
- Add new methods  
- Override existing methods  

---

🔹 Method Overriding

    class Parent {
        void show() {
            System.out.println("Parent");
        }
    }

    class Child extends Parent {
        @Override
        void show() {
            System.out.println("Child");
        }
    }

---

🔹 Types of Inheritance

- Single → A → B  
- Multilevel → A → B → C  
- Hierarchical → A → B, C  

❌ Multiple inheritance not allowed (classes)

---

🔹 Access Modifiers

| Modifier   | Inherited? | Access |
|------------|-----------|--------|
| private    | ❌ No     | Only same class |
| default    | ✅ Yes    | Same package |
| protected  | ✅ Yes    | Same package + subclasses |
| public     | ✅ Yes    | Everywhere |

---

🔹 Why Use Inheritance?

- Code reuse  
- Reduce duplication  
- Easy maintenance  
- Supports polymorphism  

---

🔹 Summary

- Use `extends`  
- Child gets parent features  
- Can override behavior  
- Only one parent allowed  

---

# Polymorphism in Java

## 📌 What is Polymorphism?

Polymorphism means **"many forms"**.

👉 Same method → different behavior  

---

## 📌 Core Idea

Supertype = Subtypes  

    void updateProfile(User u) {}

---

## 📌 Reference vs Object Type

    User user = new Editor();

- Reference → User  
- Object → Editor  

---

## 📌 Important Rule

👉 Reference decides accessible methods  
👉 Object decides executed method  

---

## 📌 Example

    class User {
        void postAReview() {
            System.out.println("User review");
        }
    }

    class Staff extends User {
        void postAReview() {
            System.out.println("Staff review");
        }
    }

    class Editor extends Staff {
        void postAReview() {
            System.out.println("Editor review");
        }
    }

---

## 📌 Runtime Example

    User user = new Editor();
    user.postAReview();  // Editor

---

## 📌 Types

### Compile-Time (Overloading)

    int add(int a, int b) {}
    double add(double a, double b) {}

### Runtime (Overriding)

    class A { void show() {} }
    class B extends A { void show() {} }

---

## 📌 Summary

- One reference → many behaviors  
- Uses inheritance  
- Clean & flexible  

---

# Abstraction in Java

🔹 What is Abstraction?  

👉 Hiding implementation details and showing only essential features  

👉 Focus: **What to do, not how to do**

---

🔹 Achieved Using:

- Abstract classes  
- Interfaces  

---

🔹 Abstract Class Example

    abstract class Vehicle {
        abstract void start();

        void stop() {
            System.out.println("Vehicle stopped");
        }
    }

    class Car extends Vehicle {
        void start() {
            System.out.println("Car starts with key");
        }
    }

---

🔹 Interface Example

    interface Animal {
        void sound();
    }

    class Dog implements Animal {
        public void sound() {
            System.out.println("Bark");
        }
    }

---

🔹 Key Points

- Cannot create object of abstract class  
- Can have abstract + normal methods  
- Interface → only method definitions (mostly)  

---

🔹 Why Abstraction?

- Reduce complexity  
- Improve maintainability  
- Hide internal logic  

---

🔹 Summary

- Hides implementation  
- Shows only important parts  
- Achieved using abstract class & interface  

---

# Encapsulation in Java

🔹 What is Encapsulation?  

👉 Wrapping data (variables) and code (methods) into one unit  

👉 Also called **Data Hiding**

---

🔹 Example

    class Person {
        private String name;

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }
    }

---

🔹 Why Private?

👉 To protect data from direct access  

---

🔹 Benefits

- Data security  
- Control over data  
- Flexible & maintainable  

---

🔹 Real Use

    Person p = new Person();
    p.setName("Afzal");
    System.out.println(p.getName());

---

🔹 Summary

- Use private variables  
- Use getters & setters  
- Protect data  

---

# 🔥 Final Summary (ALL OOP)

| Concept        | Meaning |
|---------------|--------|
| Inheritance   | Reuse code |
| Polymorphism  | Many forms |
| Abstraction   | Hide details |
| Encapsulation | Protect data |

---

# 🚀 Golden Line

👉 OOP makes code:
- Reusable  
- Secure  
- Flexible  
- Maintainable  

---