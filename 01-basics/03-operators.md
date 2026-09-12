# Operators in Java

> **Section**: Basics  
> **Topic**: 03 — Operators  
> **Last Updated**: 2026-09-13  
> **Status**: ✅ Complete

---

## 📌 What You'll Learn

- [What operators are and why they matter](#what-is-operator-)
- [The **types** of operators in Java (Arithmetic, Relational, Logical, etc.)](#type-of-operators)
- How **Operator Precedence** and **Associativity** work
- The relationship between Type Conversion, Casting, and operators
- Real-world examples and common mistakes

---

### What is Operator ?

Operators are special symbols that perform specific operations on one,
two, or three operands, and then return a result.

### What is Operand ?

Operand are something on that operators can be applied.

### Type of operators

| #  | Types of operators                                                 |
|----|--------------------------------------------------------------------|
| 01 | [Arithmetic Operators](#1-arithmetic-operator)                     | 
| 02 | [Increment/Decrement Operators](#2-increment--decrement-operators) | 
| 03 | [Concatenation Operators](#3-concatenation-operators)              | 
| 04 | [Relational Operators](#4-relational-operators)                    | 
| 05 | [Equality Operators](#5-equality-operators)                        | 
| 06 | [Bitwise Operators](#6-bitwise-operators)                          | 
| 07 | [Logical Operators](#7-logical-operator)                           | 
| 08 | [Assignment Operators](#8-assignment-operators)                    | 
| 09 | [Ternary Operator](#9-ternary-operator)                            | 
| 10 | [Operator Precedence](#operator-precedence-and-associativity)      | 

---

### 💡 Example

```java
public class OperatorsDemo {
    public static void main(String[] args) {
        int a = 10, b = 3;
//        Arithmetic Operators
        System.out.println("Sum       : " + (a + b));   // 13
        System.out.println("Difference: " + (a - b));   // 7
        System.out.println("Product   : " + (a * b));   // 30
        System.out.println("Quotient  : " + (a / b));   // 3
        System.out.println("Remainder : " + (a % b));   // 1

//        Concatenation Operators
        System.out.println("shivam " + "vashishtha"); // output: shivam vashishtha

//        Relational Operators
        System.out.println("a > b     : " + (a > b));   // true
        System.out.println("a == b    : " + (a == b));  // false

//        Logical Operators
        boolean x = true, y = false;
        System.out.println("x && y    : " + (x && y));  // false
        System.out.println("x || y    : " + (x || y));  // true

//        Assignment Operators
        a += 5;              // a = 10 + 5 = 15
        System.out.println("After += : " + a);

        a -= 3;              // a = 15 - 3 = 12
        System.out.println("After -= : " + a);

        a *= 2;              // a = 12 * 2 = 24
        System.out.println("After *= : " + a);

        a /= 4;              // a = 24 / 4 = 6
        System.out.println("After /= : " + a);

        a %= 4;              // a = 6 % 4 = 2
        System.out.println("After %= : " + a);

//        Ternary operator
        int max2 = (a > b) ? a : b;
        System.out.println("Max: " + max2);  // 20
    }
}
```

### 1. Arithmetic Operator

- The **arithmetic operator** are `+  -  *  /  %`
- if we apply any arithmetic operator between two variables `a` and `b` then
  result type is always ` Max(int, typeof a, typeof b`.
- `/ %` are the two operators which causes Arithmetic Exception.
- [Arithmetic operator example](#-example)

> - byte + byte = int
>- byte + short = int
>- int + long = long
>- long + float = float
>- double + char = double
>- char + char = int

> Note: In case of Infinity and NaN
>- In the case of integral arithmetic (int, short,long, byte). There is no way to represent infinity and NaN. Hence, if
   the infinity or NaN is the result, we will get Arithmetic Exception.
>- But in case of floating point arithmetic (float,double). There is a way to represent infinity and NaN, Float and
   Double classes contains the two constants for infinity (Infinity, -Infinity) and one constant for NaN (NaN).

### 2. Increment & Decrement Operators

**Increment Operator `++`**: It increases a value one time.  
**Decrement Operator `--`**: It decreases a value one time.

- There are two types of **Increment and Decrement** operators.
    - **pre** → first mutate the value then use.
    - **post** → first use the value then mutate

```java
private void incDecOperator() {
    int a = 10;
// pre-increment  
    System.out.println(++a); // output: 11  
// post-increment - here a = 11  
    System.out.println(a++); // output: 11  
// here a = 12
}
//    This thing same goes with Decrement
```

### 3. Concatenation Operators

- It is the only overloaded operator in java `+`.
- It acts as a **Concatenation Operators** when we use it with `String`
- [Concatenation Operators example](#-example)

### 4. Relational Operators

- The **Relational Operators** are `> < >= <=`.
- These operators can be use only on primitives except boolean and return boolean.
- Nesting of these operators are not allowed.

```java
private void relationalOp() {
    10 > 20 //false
    'a' > 'b' //true
    10 >= 10.0 //true
    'a' > 125 //true
    true >= true //CE: can't be applied on boolean
//    10 < 20 < 30 //CE:
}
```

### 5. Equality Operators

- **Equality Operators** are `== !=`.
- These two operators can be applied on every primitive and object references.
- If we apply equality operator on primitive. it compares the values.

```java
private void equalityOp() {
    10 == 10.0 // ture
    'a' == 97 // ture
    true == false // false
    10.5 == 12.3 // false
}
```

- If we apply equality operator on Object. it compares the reference/address.
- It returns false while null comparison.

```java
private void equalityOp() {
    Object ob1 = new Object();
    Object ob2 = new Object();
    Object ob3 = ob1;
    System.out.println(ob1 == ob2); // false
    System.out.println(ob1 == ob3); // true
    System.out.println(ob1 == null); // false
    System.out.println(null == null); // true
}
```

- To apply equality operators between object reference, three should be some relationship between argument types, either
  parent-child or same type otherwise we will get compile time error **InComparable** types.

### 6. Bitwise Operators

- Bitwise operators work at the **binary (0 and 1)** level. They operate on individual bits, making them fast and useful
  for low-level programming, flags, and optimization.

🧩 Bitwise Operators List

| Operator | Name                 | Example   | What it does                       |
|----------|----------------------|-----------|------------------------------------|
| `&`      | Bitwise AND          | `a & b`   | 1 if both bits are 1               |
| `\|`     | Bitwise OR           | `a \| b`  | 1 if any bit is 1                  |
| `^`      | Bitwise XOR          | `a ^ b`   | 1 if bits are different            |
| `~`      | Bitwise NOT          | `~a`      | Inverts all bits                   |
| `<<`     | Left Shift           | `a << 2`  | Shifts bits left                   |
| `>>`     | Right Shift (signed) | `a >> 2`  | Shifts bits right (preserves sign) |
| `>>>`    | Unsigned Right Shift | `a >>> 2` | Shifts bits right (zero fill)      |

### 🔍 Truth Tables

### AND `&`

| a | b | a & b |
|---|---|-------|
| 0 | 0 | 0     |
| 0 | 1 | 0     |
| 1 | 0 | 0     |
| 1 | 1 | 1     |

### OR `|`

| a | b | a \| b |
|---|---|--------|
| 0 | 0 | 0      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 1      |

### XOR `^`

| a | b | a ^ b |
|---|---|-------|
| 0 | 0 | 0     |
| 0 | 1 | 1     |
| 1 | 0 | 1     |
| 1 | 1 | 0     |

### NOT `~`

| a | ~a |
|---|----|
| 0 | 1  |
| 1 | 0  |

### 💻 Examples (See in Binary)

```java
private void method() {
    int a = 5;   // binary: 0101
    int b = 3;   // binary: 0011

    System.out.println(a & b);   // 0001 = 1
    System.out.println(a | b);   // 0111 = 7
    System.out.println(a ^ b);   // 0110 = 6
    System.out.println(~a);      // ...11111010 = -6
    System.out.println(a << 1);  // 1010 = 10
    System.out.println(a >> 1);  // 0010 = 2
}
```

### 7. Logical Operator

- Logical operators are used to combine **boolean expressions** and make decisions. They are the backbone of `if`,
  `while`, and `for` conditions.
- `&& ||` → `AND OR` are also known as **short circuit operator**.
- `!` is also known as **boolean complement operator**.
- **Short Circuit Operator**: Returns true if only both conditions are true.
- **Boolean Complement Operator**: Reverses the boolean value.
- [Logical operator example](#-example)

### 8. Assignment Operators

- Assignment operators are used to **assign values** to variables. Java has one simple assignment operator (`=`) and
  several **compound assignment operators** that combine an operation with assignment.

**🧩 Assignment Operators List**

| Operator | Name                            | Example    | Same as       |
|----------|---------------------------------|------------|---------------|
| `=`      | Simple Assignment               | `a = 10`   | `a = 10`      |
| `+=`     | Add and Assign                  | `a += 5`   | `a = a + 5`   |
| `-=`     | Subtract and Assign             | `a -= 5`   | `a = a - 5`   |
| `*=`     | Multiply and Assign             | `a *= 5`   | `a = a * 5`   |
| `/=`     | Divide and Assign               | `a /= 5`   | `a = a / 5`   |
| `%=`     | Modulus and Assign              | `a %= 5`   | `a = a % 5`   |
| `&=`     | Bitwise AND and Assign          | `a &= 5`   | `a = a & 5`   |
| `\|=`    | Bitwise OR and Assign           | `a \|= 5`  | `a = a \| 5`  |
| `^=`     | Bitwise XOR and Assign          | `a ^= 5`   | `a = a ^ 5`   |
| `<<=`    | Left Shift and Assign           | `a <<= 2`  | `a = a << 2`  |
| `>>=`    | Right Shift and Assign          | `a >>= 2`  | `a = a >> 2`  |
| `>>>=`   | Unsigned Right Shift and Assign | `a >>>= 2` | `a = a >>> 2` |

- [Assignment operator example](#-example)

### 9. Ternary Operator

- The ternary operator (`? :`) is Java's only **three-operand operator**. It is a **shortcut for `if-else`** that
  returns a value. It makes simple conditional logic concise and readable.

> Syntax: result = (condition) ? valueIfTrue : valueIfFalse;

- [Ternary Operator example](#-example)

---

### Operator Precedence and Associativity

- **Operator precedence** decides which operator is evaluated first in an expression.
- **Associativity** decides the order when two operators have the same precedence. Getting this wrong leads to silent
  bugs.

### 📊 Complete Precedence Table

**Top = highest precedence** (pehle evaluate hoga)

| Level | Operators                                                       | Associativity | Category         |
|-------|-----------------------------------------------------------------|---------------|------------------|
| 1     | `()` `[]` `.` `::`                                              | Left → Right  | Postfix / Access |
| 2     | `++` `--` `!` `~` `+` `-` `(type)` `new`                        | Right → Left  | Unary            |
| 3     | `*` `/` `%`                                                     | Left → Right  | Multiplicative   |
| 4     | `+` `-`                                                         | Left → Right  | Additive         |
| 5     | `<<` `>>` `>>>`                                                 | Left → Right  | Shift            |
| 6     | `<` `<=` `>` `>=` `instanceof`                                  | Left → Right  | Relational       |
| 7     | `==` `!=`                                                       | Left → Right  | Equality         |
| 8     | `&`                                                             | Left → Right  | Bitwise AND      |
| 9     | `^`                                                             | Left → Right  | Bitwise XOR      |
| 10    | `\|`                                                            | Left → Right  | Bitwise OR       |
| 11    | `&&`                                                            | Left → Right  | Logical AND      |
| 12    | `\|\|`                                                          | Left → Right  | Logical OR       |
| 13    | `? :`                                                           | Right → Left  | Ternary          |
| 14    | `=` `+=` `-=` `*=` `/=` `%=` `&=` `\|=` `^=` `<<=` `>>=` `>>>=` | Right → Left  | Assignment       |

---

### 🧠 Trick

> **Unary → Multiplicative → Additive → Shift → Relational → Equality → Bitwise → Logical → Ternary → Assignment**

**Short form**: **U-M-A-S-R-E-B-L-T-A**

---

### (Quick Overview)

| Type           | Operators                  | Example         |
|----------------|----------------------------|-----------------|
| **Arithmetic** | `+  -  *  /  %`            | `a + b`         |
| **Increment**  | `++`                       | `a++`           |
| **Decrement**  | `--`                       | `a--`           |
| **Relational** | `>  <  >=  <=`             | `a > b`         |
| **Equality**   | `== !=`                    | `a == b`        |
| **Bitwise**    | `&  \|  ^  ~  <<  >>  >>>` | `a & b`         |
| **Logical**    | `&&  \|\|  !`              | `a && b`        |
| **Assignment** | `=  +=  -=  *=  /=  %=`    | `a += 5`        |
| **Ternary**    | `? :`                      | `a > b ? a : b` |

[← Previous Variable and data types](02-variables-and-data-types.md) | [Back to Index](README.md) | [Next: Conditionals →](04-conditionals.md)
