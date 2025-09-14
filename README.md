# Inheritance in C++

##  Overview
Inheritance is a fundamental concept in **Object-Oriented Programming (OOP)** that allows a class to acquire properties and behaviors of another class.  
- The class that inherits is called the **derived class** (child class).  
- The class from which properties are inherited is called the **base class** (parent class).  
- Inheritance promotes **code reusability**, **extensibility**, and **modular design**.

---

##  Theory

### What is Inheritance?
- Inheritance allows a class to **reuse data members and member functions** of another class.  
- It establishes an **“is-a” relationship** between classes.  
- In C++, inheritance is implemented using the **colon (:) syntax**.

```cpp
class Derived : access_specifier Base {
    // Body of derived class
};
```
# Types of Inheritance in C++

## 📖 Overview
Inheritance in C++ allows a **derived class** to acquire properties and behaviors of a **base class**.  
It models **“is-a” relationships** and promotes **code reusability**.  
C++ supports multiple types of inheritance to represent different real-world relationships.

---

##  Types of Inheritance

### 1. Single Inheritance
- One derived class inherits from **one base class**.  
- Example:  
```cpp
class Base { };
class Derived : public Base { };
```

### 2. Multiple Inheritance
- In multiple inheritance, a derived class has **more than one parent class**.  
- Syntax:
```cpp
class Derived : access_specifier Base1, access_specifier Base2 {
    // Body of derived class
};
```

### 3. Multilevel Inheritance
- In multilevel inheritance, class relationships follow a **parent → child → grandchild** hierarchy.  
- Syntax:
```cpp
class Base {
    // Base class members
};

class Derived1 : public Base {
    // Derived class 1 members
};

class Derived2 : public Derived1 {
    // Derived class 2 members
};
```

### 4. Hierarchical Inheritance
- In hierarchical inheritance, a single **base class** is extended by **two or more derived classes**.  
- Syntax:
```cpp
class Base {
    // Base class members
};

class Derived1 : public Base {
    // Derived class 1 members
};

class Derived2 : public Base {
    // Derived class 2 members
};
```

### 5. Hybrid Inheritance
 Hybrid inheritance combines different inheritance types in one program.  
- It allows derived classes to inherit features from multiple base classes while maintaining a clear hierarchy.  
- **Diamond Problem**:
  - Occurs in multiple inheritance when a class inherits the same base class through multiple paths.  
  - Solved using the `virtual` keyword.

### Syntax Example:
```cpp
class A { };
class B : virtual public A { };
class C : virtual public A { };
class D : public B, public C { };
```

# Program Summary

##  Single Inheritance 
- This program demonstrates **single inheritance** in C++.  
- `Resident` is the **base class** with:
  - Data member: `country`  
  - Member function: `place()` which prints the city name.  
- `Work` is the **derived class** that inherits publicly from `Resident` and adds its own data member:
  - `college`  

- In `main()`, an object of `Work` is created, and the program accesses:
  - The inherited function `place()` from `Resident`  
  - The inherited data member `country`  
  - Its own data member `college`  

- This demonstrates how **derived classes can reuse properties and functions of base classes**.

---

###  Algorithm
1. **Start** the program.  
2. Define **base class** `Resident` with:
   - `string country = "India";`
   - Member function `place()` that prints `"Pune"`.  
3. Define **derived class** `Work` that **inherits publicly** from `Resident` and adds:
   - `string college = "Symbiosis Institute of Technology";`  
4. In `main()`:
   - Create an object `w` of class `Work`.  
   - Call `w.place()` → prints `"Pune"`.  
   - Access `w.country` → prints `"India"`.  
   - Access `w.college` → prints `"Symbiosis Institute of Technology"`.  
5. **End** the program.  

---

##  Multiple Inheritance 
- This program demonstrates **multiple inheritance** in C++.  
- There are three classes:  
  1. **Person** (base class)  
     - Data member: `name`  
     - Member function: `displayName()`  
  2. **Employee** (base class)  
     - Data members: `id_no`, `salary`  
     - Member functions: `displayId()`, `displaySalary()`  
  3. **Staff** (derived class)  
     - Inherits publicly from **Person** and **Employee**  
     - Adds its own data member: `field`  
     - Member function: `displayDetails()` to display all details  

- In `main()`, an object of `Staff` is created, values are assigned to its members, and all details are displayed using `displayDetails()`.  
- This shows how a derived class can **combine features from multiple base classes**.

---

###  Algorithm
1. **Start** the program.  
2. Define **base class** `Person` with:  
   - `string name`  
   - Function `displayName()` to print the name  
3. Define **base class** `Employee` with:  
   - `int id_no`, `double salary`  
   - Functions `displayId()` and `displaySalary()` to print id and salary  
4. Define **derived class** `Staff` that **inherits publicly** from `Person` and `Employee` and adds:  
   - `string field`  
   - Function `displayDetails()` that calls inherited functions and prints `field`  
5. In `main()`:
   - Create object `staff` of class `Staff`  
   - Assign values to `staff.name`, `staff.id_no`, `staff.salary`, and `staff.field`  
   - Call `staff.displayDetails()` to display all information  
6. **End** the program.  

---

##  Multilevel Inheritance
- This program demonstrates **multilevel inheritance** in C++.  
- There are three classes forming a **chain of inheritance**:  
  1. **Actor** (base class)  
     - Data member: `name`  
     - Member function: `displayName()`  
  2. **BollywoodActor** (derived from `Actor`)  
     - Data member: `debutYear`  
     - Member function: `displayDebutYear()`  
  3. **AwardWinningActor** (derived from `BollywoodActor`)  
     - Data member: `awardsWon`  
     - Member function: `displayDetails()` to display all attributes  

- In `main()`, an object of `AwardWinningActor` is created, values are assigned, and `displayDetails()` is called to show the complete information.  
- This shows how a derived class can **inherit and extend members from multiple levels of base classes**.

---

###  Algorithm
1. **Start** the program.  
2. Define **base class** `Actor` with:  
   - `string name`  
   - Function `displayName()` to print the actor's name  
3. Define **derived class** `BollywoodActor` that inherits from `Actor` with:  
   - `int debutYear`  
   - Function `displayDebutYear()` to print the debut year  
4. Define **derived class** `AwardWinningActor` that inherits from `BollywoodActor` with:  
   - `int awardsWon`  
   - Function `displayDetails()` that calls `displayName()` and `displayDebutYear()` and prints `awardsWon`  
5. In `main()`:
   - Create object `actor` of class `AwardWinningActor`  
   - Assign values to `actor.name`, `actor.debutYear`, and `actor.awardsWon`  
   - Call `actor.displayDetails()` to display all information  
6. **End** the program.  

---

##  Hierarchical Inheritance
- This program demonstrates **hierarchical inheritance** in C++.  
- A single **base class** `Person` is inherited by **multiple derived classes**: `Student`, `Teacher`, and `Staff`.  
- **Base Class: Person**  
  - Data members: `name`, `age`  
  - Member functions: `inputDetails()`, `displayDetails()`  
- **Derived Classes:**  
  1. `Student` → Adds `rollNo` and functions to input/display student details  
  2. `Teacher` → Adds `subject` and functions to input/display teacher details  
  3. `Staff` → Adds `department` and functions to input/display staff details  

- Each derived class can **reuse the properties and functions of `Person`** while adding its own specific attributes.  

---

###  Algorithm
1. **Start** the program.  
2. Define **base class** `Person` with:
   - Data members: `name`, `age`  
   - Functions: `inputDetails()` to read name and age, `displayDetails()` to print them  
3. Define **derived class** `Student` that inherits from `Person`:
   - Data member: `rollNo`  
   - Functions: `inputStudent()` and `displayStudent()`  
4. Define **derived class** `Teacher` that inherits from `Person`:
   - Data member: `subject`  
   - Functions: `inputTeacher()` and `displayTeacher()`  
5. Define **derived class** `Staff` that inherits from `Person`:
   - Data member: `department`  
   - Functions: `inputStaff()` and `displayStaff()`  
6. In `main()`:
   - Create objects `s`, `t`, `st` of classes `Student`, `Teacher`, `Staff`  
   - Call input functions to take details from the user  
   - Call display functions to show the respective details  
7. **End** the program.  

---

##  Inheritance with Access Specifiers
- This program demonstrates **multiple inheritance** in C++ along with **access specifiers** (`private`, `protected`, `public`).  
- Classes involved:  
  1. **Person**  
     - Data members: `name` and `address` (protected)  
     - Member functions: `displayName()`, `displayAddress()`  
  2. **Employee**  
     - Data member: `id` (protected), `salary` (private)  
     - Member functions: `displayId()`, `displaySalary()`  
  3. **Staff** (derived from `Person` and `Employee`)  
     - Adds data member `field` (private)  
     - Function `displayDetails()` prints all accessible members  

- **Key point:**  
  - `private` members of a base class **cannot be accessed directly** from the derived class or main function.  
  - `protected` and `public` members are accessible according to the inheritance type.  

---

###  Algorithm
1. **Start** the program.  
2. Define **base class `Person`**:
   - Protected members: `name`, `address`  
   - Public functions: `displayName()`, `displayAddress()`  
3. Define **base class `Employee`**:
   - Protected member: `id`  
   - Private member: `salary`  
   - Public functions: `displayId()`, `displaySalary()`  
4. Define **derived class `Staff`** that inherits from `Person` and `Employee`:
   - Private member: `field`  
   - Constructor initializes all base class members and `field`  
   - Function `displayDetails()` calls inherited functions to display information  
5. In `main()`:
   - Create object `staff` of class `Staff`  
   - Call `staff.displayDetails()` to display all accessible information  
   - **Do not attempt to access `private` members** (like `salary`) directly in `main()`  
6. **End** the program.  

---

##  Conclusion

- **Inheritance** is a fundamental concept of object-oriented programming that allows **derived classes to reuse and extend the functionality of base classes**.  
- It promotes **code reusability**, **modularity**, and **scalability**, making programs easier to maintain.  
- Proper use of **access specifiers** ensures **data encapsulation** and **controlled access** to class members.  
- Understanding the **types of inheritance** (single, multiple, multilevel, hierarchical, and hybrid) is essential for designing **robust and efficient class hierarchies**.  
- Inheritance enables modeling of **real-world relationships** effectively, reducing code duplication and supporting polymorphism in C++ programs.
