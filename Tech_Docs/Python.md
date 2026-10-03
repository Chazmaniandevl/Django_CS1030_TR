# **Python vs Java: OOP & Fundamentals Cheatsheet**

A concise technical reference comparing Object-Oriented Programming principles, type systems, and core syntax between Python and Java.

# [**Table of Contents**](#heading=h.ywqapbv9kz2u)

[1\. Executive Summary & Paradigm Overview](#1.-executive-summary-&-paradigm-overview)

[2\. Syntax & Fundamental Types](#2.-syntax-&-fundamental-types)

[3\. Class Definition & Instantiation](#3.-class-definition-&-instantiation)

[Java](#java)

[Python](#python)

[4\. Constructors & Attributes](#4.-constructors-&-attributes)

[Java](#java-1)

[5\. Encapsulation & Access Control](#5.-encapsulation-&-access-control)

[Python Property Example](#python-property-example)

[Python Inheritance](#python-inheritance)

[7\. Abstract Classes & Interfaces](#7.-abstract-classes-&-interfaces)

[Python ABC Example](#python-abc-example)

[8\. Key Takeaways & Best Practices](#8.-key-takeaways-&-best-practices)

# **1\. Executive Summary & Paradigm Overview** {#1.-executive-summary-&-paradigm-overview}

Both Python and Java support Object-Oriented Programming, but they approach typing, compilation, and execution differently:

* **Java**: Statically typed, strongly compiled to bytecode running on the JVM. Everything (except primitives) lives inside classes.  
* **Python**: Dynamically typed, interpreted/JIT compiled (CPython). Multi-paradigm (supports object-oriented, procedural, and functional programming).

# **2\. Syntax & Fundamental Types** {#2.-syntax-&-fundamental-types}

| Feature / Concept | Java | Python |
| :---- | :---- | :---- |
| Primary Typing | Static typing (`int x = 10;`) | Dynamic typing (`x = 10`) |
| Primitives vs Objects | Distinct primitive types (`int`, `boolean`, `double`) vs Reference Objects | Everything is an object (`int`, `str`, `bool` are classes) |
| Code Block Structure | Curly braces `{}` | Indentation (4 spaces or tab) |
| Standard Output | `System.out.println("Hello");` | `print("Hello")` |
| Variable Declaration | Explicit type required | Implicit declaration on assignment |

# **3\. Class Definition & Instantiation** {#3.-class-definition-&-instantiation}

## **Java** {#java}

public class Student {

    // Field declaration

    private String name;

    // Main entry point

    public static void main(String\[\] args) {

        Student s \= new Student();

    }

}

## **Python** {#python}

class Student:

    \# Class instantiation does not require 'new' keyword

    pass

if \_\_name\_\_ \== "\_\_main\_\_":

    s \= Student()

# **4\. Constructors & Attributes** {#4.-constructors-&-attributes}

## **Java** {#java-1}

* Constructors share the exact class name.  
* Instance variables are explicitly declared at class scope.

a  
public class Person {  
private String name;  
private int age;public Person(String name, int age) {

    this.name \= name;

    this.age \= age  
;  
}  
}

\#\#\# Python

\* \`\_\_init\_\_\` acts as the initializer method.

\* \`self\` explicitly references the instance being initialized or operated on.

\`\`\`python

class Person:

    def \_\_init\_\_(self, name: str, age: int):

        self.name \= name

        self.age \= age

# **5\. Encapsulation & Access Control** {#5.-encapsulation-&-access-control}

| Concept | Java | Python |
| :---- | :---- | :---- |
| Access Modifiers | `public`, `protected`, `private`, package-private | Naming conventions (`_protected`, `__private`) |
| Strictness | Enforced by compiler | Encapsulation by convention ("we are all consenting adults here") |
| Getters / Setters | Explicit methods (`getName()`, `setName()`) | Decorator properties (`@property`, `@name.setter`) |

## **Python Property Example** {#python-property-example}

n  
class Account:  
def **init**(self, balance):  
self.\_balance \= balance@property

def balance(self):

    return self.\_balance

@balance.setter

def balance(self, value):

    if value \>= 0:

        self  
.\_balance \= value

\#\# 6\. Inheritance & Polymorphism

\* \*\*Java\*\*: Single class inheritance (\`extends\`), multiple interface implementation (\`implements\`).

\* \*\*Python\*\*: Multiple inheritance supported directly (\`class Child(ParentA, ParentB):\`). Method resolution order (MRO) handled via C3 linearization.

\#\#\# Java Inheritance

\`\`\`java

public class Animal {

    public void makeSound() {

        System.out.println("Animal sound");

    }

}

public class Dog extends Animal {

    @Override

    public void makeSound() {

        System.out.println("Bark");

    }

}

## **Python Inheritance** {#python-inheritance}

class Animal:

    def make\_sound(self):

        print("Animal sound")

class Dog(Animal):

    def make\_sound(self):

        print("Bark")

# **7\. Abstract Classes & Interfaces** {#7.-abstract-classes-&-interfaces}

* **Java**: Explicit `interface` and `abstract class` keywords enforced by compiler.  
* **Python**: Abstract Base Classes (ABC) module (`from abc import ABC, abstractmethod`). Protocol / Duck Typing allows structural subtyping without explicit inheritance.

## **Python ABC Example** {#python-abc-example}

from abc import ABC, abstractmethod

class Shape(ABC):

    @abstractmethod

    def area(self) \-\> float:

        pass

# **8\. Key Takeaways & Best Practices** {#8.-key-takeaways-&-best-practices}

1. **Explicit vs Implicit**: Java relies on explicit type signatures and compile-time enforcement; Python favors concise runtime dynamic evaluation and developer conventions.  
2. **`self` vs `this`**: Java implicitly passes `this`; Python requires `self` as the first argument in instance methods.  
3. **Memory & Lifecycle**: Both manage heap allocation and garbage collection automatically, but Java uses JVM memory management (G1, ZGC) while Python uses reference counting with a generational garbage collector.

