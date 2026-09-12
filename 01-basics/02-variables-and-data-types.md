# Variables & data types  in Java

> **Section**: Basics  
> **Topic**: 02 — Variables-and-data-types   
> **Last Updated**: 2026-09-12  
> **Status**: ✅ Complete

## 📌 What You'll Learn

- [What is a Variable](#what-is-a-variable)
- [What is a Data types](#what-is-a-data-type)
- [How to declare and initialize variables](#how-to-declare-and-initialize-variables)
- [Types of variables (local, instance, static)](#types-of-variables)
- [Difference between primitive and reference variables](#difference-between-primitive-and-reference-variables)
- [Where variables are stored in memory](#where-variables-are-stored-in-memory)
- [Scope and lifetime of variables](#scope-and-lifetime-of-variables)
- [Variable naming rules and conventions](#variable-naming-rules-and-conventions)
- [`var` keyword for local variable type inference](#var-keyword-for-local-variable-type-inference)

---

## 📖 Content

### What is a Variable?

A variable is a named container that stores the specific type of data in memory.

### What is a Data type?

Data type define which type of data a variable can contain.
In java, we have 8 type of primitive data types and reference data type.

```java
private void method() {
// Primitives
    byte b = 123;
    short s = 23;
    char c = 'a';
    int age = 25;
    long year = 1198L;
    float price = 10.00f;
    double finalPrice = 10.00;
    boolean bool = false;

// Reference type
    String name = "Shiva";
}
```

---

### How to Declare and Initialize Variables?

- **Declaration**: Creating a variable without assigning a value.
- **Initialization**: Assigning a value to a variable.

Syntax: To Declare and Initialize primitive variables
>
> <data_type> <varibale_name> = value;

```java
// primitive variable
public class Demo {
    int x; // declaration
    // x = 10 // wrong initialization
    int y = 10; // declaration + initialization

    private void method() {
        new Demo().x = 11;// initialization
    }
}
```

Syntax: To Declare and Initialize reference variables
> <Object_type> <variable_name> = new <Object_type>();

```java
// reference variable
public class Demo {
    Object ob1; // declaration
    Object ob2 = new Object(); // declaration + initialization

    public void method() {
        new Demo().ob1 = new Object();// initialization
    }
}
```

---

### Types of Variables

In Java, variables are classified in two ways:

- By declaration — Local, Instance, Static (3 types)
- By data type — Primitive, Reference (2 types)

**By Declaration**, there are 3 types of variables in Java:

- **Instance variables** → belong to an Object
- **Static variables** → belong to the Class
- **Local variables** → belong to a local scope

### Instance Variable

- Instance variables belong to Objects.
- Every object has a separate copy of each instance variable.
- If we don't initialize an instance variable, its value is initialized by JVM with the default value.

### Static Variable

- Static variables belong to the Class, not to objects.
- All objects share the same static variable. If one object changes its value, the change reflects in all objects.
- If we don't initialize a static variable, its value is initialized by JVM with the default value.

### Local Variable

- These variables belong to a local scope — inside loops, conditionals, blocks, or methods.
- We must initialize a local variable before using it, otherwise the compiler throws a compile-time error.

**By data type**, there are 2 types of variables in Java:

- **Primitive variables**: Primitive variables are variables that store the actual value directly
- **Reference variables**: Reference variables are variables that store the address of the Objects.

---

### Difference Between Primitive and Reference Variables

| **Feature**       | **Primitive**            | **Reference**                 |
|-------------------|--------------------------|-------------------------------|
| **Stores**        | Actual value             | Address of object             |
| **Memory**        | Stack                    | Stack (ref) + Heap (object)   |
| **Default**       | 0, 0.0, false            | null                          |
| **Can be null?**  | ❌ No                    | ✅ Yes                        |
| **Methods**       | ❌ No                    | ✅ Yes                        |
| **`==` compares** | Values                   | Addresses                     |
| **Examples**      | `int`, `char`, `boolean` | `String`, `arrays`, `objects` |

### Primitive Example

```java
int age = 25;   // value directly stored
```

### Reference Example

```java
String name = "Shiva";   // address stored, object in heap
```

### Key Difference — Copy Behavior

**Primitive (value copy):**

```java
public class Demo {
    int a = 10;
    int b = a;

    public void method() {
        b = 20;
        System.out.println(a);   // 10
    }
}
```

**Reference (address copy):**

```java
public class Demo {
    int[] a = {1, 2, 3};
    int[] b = a;

    public void method() {
        b[0] = 99;
        System.out.println(a[0]);  // 99
    }
}
```

### Comparison

- Primitives: `==` compares values
- References: `==` compares addresses; use `.equals()` for content

```java
public class Demo {
    String s1 = new String("Hello");
    String s2 = new String("Hello");

    public void method() {
        System.out.println(s1 == s2);        // false
        System.out.println(s1.equals(s2));   // true
    }
}
```

### Wrapper Classes

Every primitive has a wrapper class — `int` → `Integer`, `char` → `Character`, etc.
Autoboxing and unboxing bridge the two.

---

### Where Variables Are Stored in Memory

Java memory is divided into **Stack**, **Heap**, and **Metaspace**. Where a variable is stored depends on its **type**
(primitive vs reference) and **kind** (local, instance, static).

| **Variable Type**      | **Stored In**                         | **What's Stored** |
|------------------------|---------------------------------------|-------------------|
| **Local primitive**    | Stack                                 | Actual value      |
| **Local reference**    | Stack (reference) + Heap (object)     | Address + object  |
| **Instance primitive** | Heap (inside object)                  | Actual value      |
| **Instance reference** | Heap (inside object) + Heap (object)  | Address + object  |
| **Static primitive**   | Heap (Method Area / Metaspace)        | Actual value      |
| **Static reference**   | Heap (Method Area / Metaspace) + Heap | Address + object  |

### Key Points

- **Local variables** → Stack (both primitive and reference)
- **Instance variables** → Heap (inside the object)
- **Static variables** → Metaspace (Method Area)
- **Objects** (referenced by any reference variable) → always Heap
- **String literals** → String Constant Pool (part of Heap)

### Example

```java
public class Demo {
    static int staticCount = 0;      // static primitive → Metaspace
    int instanceAge = 25;            // instance primitive → Heap
    String instanceName = "B";       // instance reference → Heap + Heap

    public void method() {
        int localX = 10;             // local primitive → Stack
        String localName = "C";      // local reference → Stack + Heap
    }
}
```

---

### Scope and lifetime of variables

- **Scope** — It defines where a variable is accessible in code (where you can use it).
- **Lifetime** — how long a variable stays in memory (when it is created and
  destroyed).

**Local Variable Scope**: A local variable is accessible only within the
block/method where it is declared. Using it outside causes a compile-time error.

**Instance Variable Scope**: An instance variable is accessible throughout the
class (methods, constructors, blocks).
> To access: Through an object (person.age).

**Static Variable Scope**: A static variable is also accessible throughout the
class, but accessed through the ClassName.

---

### Variable naming rules and conventions

Java has two levels of naming guidance:

- **Rules** — must be followed (compile error otherwise)
- **Conventions** — recommended (for clean, readable code)

| Rule/Convention                  | Type       | Example              |
|----------------------------------|------------|----------------------|
| Start with letter, `$`, `_`      | Rule       | `int age;`           |
| Cannot start with digit          | Rule       | `int 1age;` ❌       |
| Cannot be keyword                | Rule       | `int class;` ❌      |
| Case-sensitive                   | Rule       | `age` ≠ `Age`        |
| No spaces                        | Rule       | `int myAge;`         |
| `camelCase` for variables        | Convention | `int userAge;`       |
| `UPPER_SNAKE_CASE` for constants | Convention | `final int MAX_AGE;` |
| Meaningful names                 | Convention | `int customerAge;`   |
| Boolean as question              | Convention | `boolean isActive;`  |

---

### `var` keyword for local variable type inference

`var` (Java 10+) lets the compiler infer the type of local variable from its initializer.

```java
private void method() {
    var age = 25;           // int
    var name = "Shivam";    // String
    var price = 99.99;      // double
}
```

### Rules

1. **Only for local variables**

```java
   public void method() {
    var x = 10;   // OK
}
```

2. **Initialization is required**

```java
private void method() {
    var x = 10;   // OK
    var y;        // ERROR
}
```

3. **Cannot be `null`**

```java
private void method() {
    var x = null;   // ERROR
}
```

4. **Cannot be used with lambdas or array literals**

```java
private void method() {
    var lambda = () -> {
    };      // ERROR
    var arr = {1, 2, 3};         // ERROR
    var arr = new int[]{1, 2, 3};  // OK
}
```

5. **Type is fixed after inference**

```java
private void method() {
    var x = 10;      // x is int
    x = "Hello";     // ERROR
}
```

### When to Use

- ✅ When the type is obvious: `var name = "Shivam";`
- ✅ For long generic types: `var map = new HashMap<String, List<Integer>>();`
- ❌ When the type is unclear: `var x = getValue();`

### Examples

```java
private void method() {
  var list = new ArrayList<String>();
  var map = new HashMap<String, Integer>();
  var numbers = List.of(1, 2, 3);
  for (var num : numbers) {
    System.out.println(num);
  }
}
```

### `var` vs Explicit Type

| Feature        | Explicit        | `var`                |
|----------------|-----------------|----------------------|
| Syntax         | `int age = 25;` | `var age = 25;`      |
| Type detection | Manual          | Automatic            |
| Use case       | Always          | When type is obvious |

### Common Mistakes

- Using `var` without initialization
- Using `var` for instance/static variables
- Assigning `null` to `var`
- Using `var` with lambdas or array literals

---


[← Previous: Introduction to Java](01-introduction.md) | [Back to Index](README.md) | [Next: Operators →](03-operators.md)
