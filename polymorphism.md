## **polymorphism**
A complete polymorphism cheatsheet with code examples and explanations are provided below:

Polymorphism is one of the fundamental concepts in object-oriented programming (OOP) that allows objects of different classes to be treated as objects of a common superclass. It enables code to be written in a generic manner, making it more flexible and reusable.

1.  **Polymorphism Overview**: Polymorphism refers to the ability of objects of different types to be treated as objects of a common type. It allows for flexibility and extensibility in the design of software systems.
    
2.  Types of Polymorphism: 
  
    a. **Compile-time Polymorphism (Static Polymorphism)**
    
    *   Achieved through **function overloading** and **operator overloading**.
    *   Resolved at compile-time based on the type and number of arguments.
    
    b. **Runtime Polymorphism (Dynamic Polymorphism)**
    
    *   Achieved through **function overriding** and **virtual functions**.
    *   Resolved at runtime based on the actual object type.
3.  **Function Overloading:** Function overloading allows multiple functions with the same name but different parameters to coexist within the same class or namespace.
    

Example:


```
class MathOperations {
public:
    int add(int a, int b) {
        return a + b;
    }
    
    float add(float a, float b) {
        return a + b;
    }
};

MathOperations math;
int result1 = math.add(2, 3);         // Calls the int add(int, int)
float result2 = math.add(2.5f, 3.7f); // Calls the float add(float, float)
```
Explanation: In the above example, the `MathOperations` class has two `add` functions with different parameter types. When calling the `add` function, the compiler determines the appropriate function to invoke based on the arguments provided.

4.  **Operator Overloading:** Operator overloading allows the operators in a programming language to be used with user-defined types. It enables the behavior of operators to be customized for specific classes.

Example:

```
class Vector {
public:
    int x, y;
    
    Vector operator+(const Vector& other) {
        Vector result;
        result.x = this->x + other.x;
        result.y = this->y + other.y;
        return result;
    }
};

Vector v1{2, 3};
Vector v2{4, 5};
Vector sum = v1 + v2; // Calls the overloaded operator+
```
Explanation: In the above example, the `+` operator is overloaded for the `Vector` class. The overloaded `operator+` function adds the corresponding components of two `Vector` objects and returns the result.

5.  **Function Overriding:** Function overriding allows a derived class to provide a different implementation of a virtual function that is already defined in its base class. It enables polymorphic behavior and dynamic dispatch.

Example:


```
class Shape {
public:
    virtual void draw() {
        cout << "Drawing a generic shape." << endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing a circle." << endl;
    }
};

Shape* shape = new Circle();
shape->draw(); // Calls the overridden draw() function in Circle class

```
Explanation: In the above example, the `Shape` class defines a virtual function `draw()`. The `Circle` class overrides this function with its own implementation. When calling `draw()` on a `Shape*` pointer pointing to a `Circle` object, the overridden `draw()` function in the `Circle` class is invoked.

6.  **Virtual Functions:** Virtual functions are functions that are declared in a base class and can be overridden in derived classes. They enable runtime polymorphism by allowing the correct function implementation to be determined at runtime based on the object's actual type.

Example:


```
class Animal {
public:
    virtual void makeSound() {
        cout << "The animal makes a generic sound." << endl;
    }
};

class Dog : public Animal {
public:
    void makeSound() override {
        cout << "The dog barks." << endl;
    }
};

class Cat : public Animal {
public:
    void makeSound() override {
        cout << "The cat meows." << endl;
    }
};

Animal* animals[] = { new Dog(), new Cat() };
for (Animal* animal : animals) {
    animal->makeSound(); // Calls the appropriate overridden function
}
```
Explanation: In the above example, the `Animal` class defines a virtual function `makeSound()`. The `Dog` and `Cat` classes override this function with their respective implementations. The array of `Animal*` pointers allows different types of animals to be stored, and when calling `makeSound()`, the correct overridden function based on the actual object type is invoked.

Polymorphism allows for writing flexible and reusable code by treating objects of different types as objects of a common type. It plays a vital role in achieving code modularity and extensibility in object-oriented programming.
