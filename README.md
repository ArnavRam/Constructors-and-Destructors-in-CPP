# Experiment 12 - Constructors and Destructors

---

## Aim
- To understand, use, and implement C++ **Constructors** and **Destructors**.
- To explore their role in object initialization, cleanup, and lifecycle management.

---

## Tools Used
- Visual Studio Code
- MinGW-w64 with g++ Compiler

---

## Theory
In C++, **constructors** and **destructors** are special member functions that automatically manage the lifecycle of an object, from its creation to its destruction.

### Constructor
A **constructor** is a special member function that is automatically invoked when an object of a class is created. Its main purpose is to initialize the object’s data members and ensure it starts in a valid state.
- **Name:** Same as the class name.
- **Return Type:** None, not even `void`.
- **Types:**
    - **Default Constructor:** Has no parameters.
    - **Parameterized Constructor:** Accepts arguments to initialize members.
    - **Copy Constructor:** Creates a new object as a copy of an existing one.

### Destructor
A **destructor** is a special member function that is automatically invoked when an object’s lifetime ends (e.g., when it goes out of scope). Its main purpose is to release resources acquired by the object, such as freeing dynamically allocated memory or closing files.
- **Name:** Same as the class name, but prefixed with a tilde (`~`).
- **Parameters:** None.
- **Overloading:** Not allowed; a class can only have one destructor.

This automated process follows the **RAII** (Resource Acquisition Is Initialization) principle, ensuring safe and automatic resource management.

---

## Algorithm / Logic

### Program 1: Default Constructor
1.  **Start**
2.  Define a class `Student` with private members `name` and `fee`.
3.  Create a default constructor (`Student()`) that prompts the user to enter the student’s name and fee and stores them.
4.  Create a `display()` method to print the stored details.
5.  In `main()`, create an object `s`. The default constructor will run automatically.
6.  Call `s.display()` to show the details.
7.  **End**

### Program 2: Parameterized Constructor
1.  **Start**
2.  Define a class `Date` with private members `d`, `m`, `y`.
3.  Create a parameterized constructor `Date(int day, int month, int year)` that assigns the arguments to the members.
4.  Create a `display()` method to print the date in `d/m/y` format.
5.  In `main()`, prompt the user for day, month, and year, then create an object `d1` by passing these values to the constructor.
6.  Call `d1.display()`.
7.  **End**

### Program 3: Copy Constructor
1.  **Start**
2.  Define a class `Student` with private members like `name` and `age`.
3.  Create a parameterized constructor to initialize these members.
4.  Create a copy constructor `Student(const Student &obj)` that copies values from the provided object and prints "Copy constructor called!".
5.  In `main()`, create an object `s1` using the parameterized constructor.
6.  Create a second object `s2` as a copy of `s1` (`Student s2 = s1;`). This will invoke the copy constructor.
7.  Display the details of both `s1` and `s2`.
8.  **End**

### Program 4: Destructor with Global Counter
1.  **Start**
2.  Declare a global integer `count = 0`.
3.  Define a class where the constructor increments `count` and the destructor decrements `count`. Both should print the current object count.
4.  In `main()`, create three objects (`aa`, `bb`, `cc`). Observe the constructor calls.
5.  Create a nested scope `{}` and create another object `dd` inside it.
6.  When the nested scope ends, `dd` is destroyed, and its destructor is called.
7.  At the end of `main()`, the remaining objects are destroyed in the reverse order of their creation.
8.  **End**

---

## Conclusion
This experiment demonstrates the critical role of constructors and destructors in managing the lifecycle of C++ objects. Constructors ensure that objects are properly initialized upon creation, preventing errors from uninitialized data. Destructors ensure that resources are properly released upon an object's destruction, preventing memory leaks and other issues. Together, they implement the RAII principle, which is fundamental to writing safe, clean, and robust C++ code.
