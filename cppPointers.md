In C++, pointers are variables that store the memory addresses of other variables 1. Here are some common methods for using pointers in C++ with examples:

1.  Declaring a pointer variable:
    

    int *p; // declares a pointer to an integer
    

2.  Assigning a value to a pointer:
    

    int x = 5;
    int *p = &x; // assigns the address of x to p
    

3.  Dereferencing a pointer to access the value it points to:
    

    int x = 5;
    int *p = &x;
    cout << *p; // prints 5 (the value of x)
    

4.  Passing a pointer to a function:
    

    void changeValue(int *p) { // function that takes a pointer to an integer
        *p = 10; // changes the value at the memory location pointed to by p to 10
    }
    int x = 5;
    int *p = &x;
    changeValue(p);
    cout << x; // prints 10 (the value changed by the function)
    

5.  Using smart pointers to manage memory allocation and deallocation:
    

    #include <memory>
    void someFunction() {
        std::unique_ptr<int> p(new int(5)); // dynamically allocates an integer and assigns its address to p
        // do something with p
    } // when someFunction exits, p is automatically deleted (no need to use delete)
    

These are just a few examples of the ways you can use pointers in C++. It is important to use pointers with care, as incorrect usage can lead to memory leaks or other types of errors.

[![](https://cdn.you.com/img/programiz.com.ico)programiz1](https://www.programiz.com/cpp-programming/pointers)
