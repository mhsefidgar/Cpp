# Cpp
Considerations 
Heap Memory Allocation:

1.  Heap Memory Allocation:
    
    *   Use the `new` operator to allocate memory on the heap.
    *   Use the `delete` operator to release memory allocated on the heap.
    *   Always use `delete` on a pointer returned by `new` to avoid memory leaks.
    *   Use `delete[]` to release memory allocated for an array.
2.  Stack Memory Allocation:
    
    *   Automatic memory allocation occurs on the stack when variables are defined.
    *   When a function returns, all stack-allocated variables are automatically released.
3.  Smart Pointers:
    
    *   Use smart pointers like `unique_ptr` and `shared_ptr` to automatically manage memory.
    *   A `unique_ptr` represents ownership of a single object and automatically deletes the object when the pointer goes out of scope.
    *   A `shared_ptr` represents shared ownership of an object and automatically deletes the object when the last `shared_ptr` pointing to the object goes out of scope.
4.  Memory Management Best Practices:
    
    *   Always initialize pointers to `nullptr` to avoid accidentally dereferencing a null pointer.
    *   Avoid using raw pointers whenever possible; prefer smart pointers or non-owning pointers (`weak_ptr`, `const T*`, etc.) instead.
    *   Always release dynamically allocated memory when it is no longer needed to avoid memory leaks.
    *   Avoid circular references between shared pointers to prevent memory leaks.

# Programing examples 

1. Dynamic Memory Allocation: 
    - `new`: To dynamically allocate memory on the heap.
    
    ```cpp
    int *ptr = new int;
    *ptr = 10;
    
    ```
    
    
    - `delete`: To free the dynamically allocated memory.
    
    ```cpp
    delete ptr;
    
    ```
    
    
2. Operator Overloading: 
    - `new` and `delete` operators can be overloaded for custom memory management.
    
    ```cpp
    void* operator new(size_t size) {
        void* ptr = malloc(size);
        return ptr;
    }
    
    void operator delete(void* ptr) {
        free(ptr);
    }
    
    ```
    
    
3. Smart Pointers: 
    - `unique_ptr`: To manage 'unique' ownership of dynamically allocated memory.
    
    ```cpp
    std::unique_ptr ptr(new int(10));
    
    ```
    
    
    - `shared_ptr`: To manage 'shared' ownership of dynamically allocated memory.
    
    ```cpp
    std::shared_ptr ptr1(new int(10));
    std::shared_ptr ptr2 = ptr1;
    
    ```
    
    
4. Memory Pools: 
    - To pre-allocate a fixed size memory pool and allocate objects from it.
    
    ```cpp
    class MemoryPool {
    public:
       MemoryPool(size_t blockSize, size_t numBlocks);
    
       void* allocate(size_t size);
       void deallocate(void* ptr);
    };
    
    MemoryPool pool(sizeof(int), 10);
    int* ptr = static_cast(pool.allocate(sizeof(int)));
    
    ```
5. Memory alignment: 
    - To align memory to a specific byte boundary.
    
    ```cpp
    alignas(32) int alignedData;
    
    ```
    
    
6. Placement new: 
    - To construct an object in pre-allocated memory.
    
    ```cpp
    char buffer[sizeof(int)];
    int* ptr = new (buffer) int(10);
    
    ```
    
    
7. Memory leak detection: 
    - Use a memory profiler like Valgrind to detect memory leaks.
    
    ```cpp
    valgrind --leak-check=yes ./myProgram
    
    ```
    
    
8. RAII (Resource Acquisition Is Initialization): 
    - To release resources automatically when an object goes out of scope.
    
    ```cpp
    class File {
    public:
       File(std::string filename) {
          file = fopen(filename.c_str(), "r");
          if (file == nullptr) {
             throw std::runtime_error("Failed to open file: " + filename);
          }
       }
    
       ~File() {
          if (file != nullptr) {
             fclose(file);
          }
       }
    
       // Other file operations.
    
    private:
       FILE* file = nullptr;
    };
    
    void readFromFile() {
       File file("data.txt");
       // File is automatically closed when it goes out of scope.
       // Read data from the file.
    }
    
    ```
    

    
    
