
## C++ Data storage types

1.  **Variables**: Variables are used to store values of different data types. They can be declared using the appropriate data type and an identifier. Here's an example:


```
int age = 25; // integer variable
double pi = 3.14159; // double variable
char grade = 'A'; // character variable
bool isStudent = true; // boolean variable 
```

2.  **Arrays**: Arrays allow storing multiple values of the same data type in a contiguous block of memory. They are declared using the data type followed by square brackets with the desired size. Here's an example:


```
int numbers[5] = {1, 2, 3, 4, 5}; // integer array
double values[3] = {1.5, 2.5, 3.5}; // double array
char name[10] = "John"; // character array (string) 
```

3.  **Pointers**: Pointers are variables that store memory addresses. They can be used to manipulate data indirectly. Pointers are declared using an asterisk (\*) followed by an identifier. Here's an example:


```
int num = 10;
int* ptr = &num; // pointer to an integer

cout << *ptr; // Output: 10 (dereferencing the pointer) 
```

4.  **References**: References provide an alternative name for an existing variable. They must be initialized when declared and cannot be changed to refer to another variable. Here's an example:


```
int age = 30;
int& refAge = age; // reference to an integer
cout << refAge; // Output: 30 
```

5.  **Structures**: Structures allow grouping multiple variables under a single name. They are declared using the `struct` keyword. Here's an example:


```
struct Person {
    string name;
    int age;
};

Person p1; // Create an instance of the structure
p1.name = "John";
p1.age = 25; 
```

6.  **Classes**: Classes are user-defined data types that encapsulate data and functions. They are declared using the `class` keyword. Here's a simplified example:


```
class Rectangle {
private:
    int length;
    int width;

public:
    void setDimensions(int len, int wid) {
        length = len;
        width = wid;
    }

    int calculateArea() {
        return length * width;
    }
};

Rectangle r;
r.setDimensions(5, 3);
int area = r.calculateArea(); // area = 15 
```

7.  **Dynamic Memory Allocation**: Dynamic memory allocation allows you to allocate memory at runtime using the `new` keyword. This is useful when you need to create variables or arrays whose sizes are determined during program execution. Here's an example:


```
int* dynamicArray = new int[5]; // dynamically allocate an integer array of size 5

dynamicArray[0] = 10;
dynamicArray[1] = 20;

delete[] dynamicArray; // free the allocated memory 
```

8.  **Standard Template Library (STL) Containers**: STL containers provide ready-to-use data structures with built-in functionality. They are part of the Standard Library and include vectors, lists, maps, queues, stacks, etc. Here's an example using a vector:


```
#include <vector>

std::vector<int> numbers; // create a vector of integers

numbers.push_back(10);
numbers.push_back(20);

int value = numbers[0]; // value = 10 
```

9.  **Enumerations**: Enumerations allow you to define a named set of values. They are useful when you have a fixed set of options or states. Here's an example:


```
enum Color {
    RED,
    GREEN,
    BLUE
};

Color selectedColor = GREEN; 
```

10.  **Unions**: Unions allow you to store different types of data in a single memory location. Only one member of the union can be active at a time. Here's an example:


```
union Data {     int intValue;     float floatValue;     char charValue; };  Data data; data.intValue = 10; int value = data.intValue;
```

11.  **File Input/Output (I/O)**: C++ provides file I/O operations to read from and write to files. You can use the `ifstream` class to read from files and the `ofstream` class to write to files. Here's an example:


```
#include <fstream>

std::ofstream outputFile("data.txt"); // create a file for writing

if (outputFile.is_open()) {
    outputFile << "Hello, World!\n";
    outputFile.close();
}

std::ifstream inputFile("data.txt"); // open a file for reading

if (inputFile.is_open()) {
    std::string line;
    while (std::getline(inputFile, line)) {
        std::cout << line << '\n';
    }
    inputFile.close();
} 
```

12.  **Dynamic Arrays with `std::vector`**: `std::vector` is a versatile container from the Standard Template Library (STL) that provides dynamic array functionality with additional features such as automatic resizing. Here's an example:


```
#include <vector>

std::vector<int> dynamicArray; // create an empty vector

dynamicArray.push_back(10); // add elements to the vector
dynamicArray.push_back(20);

int value = dynamicArray[0]; // access elements by index 
```

13.  **Strings**: C++ provides the `std::string` class for working with strings. It offers various methods for manipulating and accessing string data. Here's an example:


```
#include <string>

std::string message = "Hello, world!";

int length = message.length(); // get the length of the string
char firstChar = message[0]; // access individual characters
std::string substring = message.substr(7, 5); // extract a substring 
```

14.  **Bit Fields**: Bit fields allow you to specify the number of bits to allocate for a member within a structure or class. They are useful when you need to conserve memory. Here's an example:


```
struct Flags {
    unsigned int isReady : 1;
    unsigned int isEnabled : 1;
};

Flags myFlags;

myFlags.isReady = 1;
myFlags.isEnabled = 0; 
```

15.  **Enum Class**: C++11 introduced enum classes, which provide strong type-safety and scoping for enumerations. Enum classes prevent implicit conversions and naming collisions. Here's an example:


```
enum class Color {
    RED,
    GREEN,
    BLUE
};

Color selectedColor = Color::GREEN; 
```

16.  **Type Aliases**: Type aliases allow you to create alternative names for existing data types, improving code readability and maintainability. They are declared using the `using` keyword. Here's an example:


```
using EmployeeID = int;
EmployeeID emp1 = 1234; 
```

17.  **Constants**: Constants are variables whose values cannot be modified after initialization. You can declare them using the `const` keyword. Here's an example:


```
const int MAX_VALUE = 100; 
```

18.  **Static Variables**: Static variables are variables that retain their values across function calls. They are initialized only once and preserve their values between invocations. Here's an example:


```
void incrementCounter() {
    static int counter = 0;
    counter++;
    cout << "Counter: " << counter << endl;
}

incrementCounter(); // Output: Counter: 1
incrementCounter(); // Output: Counter: 2 
```

19.  **Constant Pointers**: Constant pointers are pointers that cannot change the memory address they point to. The value at the memory location can still be modified. Here's an example:


```
int value = 10;
int* const ptr = &value; // constant pointer to an integer

*ptr = 20; // modifying the value
cout << *ptr; // Output: 20

// ptr = nullptr; // Not allowed, cannot change the memory address 
```

20.  **Pointer to a Constant**: A pointer to a constant is a pointer that can change the memory address it points to, but the value at that memory location is constant and cannot be modified. Here's an example:


```
int value = 10;
const int* ptr = &value; // pointer to a constant integer

// *ptr = 20; // Not allowed, cannot modify the value
value = 20; // Allowed, value is not constant

cout << *ptr; // Output: 20 
```

21.  **`sizeof` Operator**: The `sizeof` operator returns the size in bytes of a type or variable. It is commonly used to determine the memory size occupied by data. Here's an example:


```
int sizeOfInt = sizeof(int); // sizeOfInt = 4 (bytes)
double sizeOfDouble = sizeof(double); // sizeOfDouble = 8 (bytes)

int array[5];
int sizeOfArray = sizeof(array); // sizeOfArray = 20 (bytes) 
```

22.  **Type Casting**: Type casting allows you to convert one type to another. C++ provides two types of casting: implicit and explicit. Here's an example:


```
double value = 3.14;
int intValue = static_cast<int>(value); // explicit cast

int num = 10;
double doubleValue = num; // implicit cast
```

These additional data storage concepts in C++ expand your understanding of pointers, constant variables, operator usage, and type casting. They offer more flexibility and control over how data is stored, accessed, and manipulated in your programs.


23.  **Smart Pointers**: Smart pointers are objects that act like pointers but provide automatic memory management. They help avoid memory leaks and deallocation errors. C++ provides three types of smart pointers: `std::unique_ptr`, `std::shared_ptr`, and `std::weak_ptr`. Here's an example:


```
#include <memory>

std::unique_ptr<int> ptr = std::make_unique<int>(10); // unique_ptr

std::shared_ptr<int> sharedPtr = std::make_shared<int>(20); // shared_ptr

std::weak_ptr<int> weakPtr = sharedPtr; // weak_ptr 
```

24.  **`const` Qualifier**: The `const` qualifier can be used to make variables, function parameters, and member functions immutable, preventing modifications to their values. Here's an example:


```
const int MAX_VALUE = 100; // constant variable

void printNumber(const int num) { // constant function parameter
    // num = 10; // Not allowed, cannot modify a constant parameter
    cout << num << endl;
}

class MyClass {
public:
    void printMessage() const { // constant member function
        // message = "Modified"; // Not allowed, cannot modify a constant member function
        cout << message << endl;
    }

private:
    const string message = "Hello";
}; 
```

25.  **Namespaces**: Namespaces allow you to organize code into separate logical groups to avoid naming conflicts. They provide a scope for identifiers. Here's an example:


```
namespace Math {
    int add(int a, int b) {
        return a + b;
    }
}

int result = Math::add(5, 3); // accessing the add() function from the Math namespace 
```

26.  **Typedef and using**: Typedef and `using` allow you to create alternative names for existing types, including user-defined types. They improve code readability and maintainability. Here's an example:


```
typedef int Number; // typedef for int
Number value = 10;

using PersonID = int; // using for int
PersonID id = 1234; 
```

27.  **`constexpr`**: The `constexpr` specifier indicates that an object or function can be evaluated at compile time. It allows the result to be used in contexts that require constant expressions. Here's an example:


```
constexpr int SQUARE(int x) {
    return x * x;
}

constexpr int value = SQUARE(5); // evaluated at compile time 
```


