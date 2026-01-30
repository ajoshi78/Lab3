# PRG210 \- Lab 3

In this lab, you will be working with Microsoft Visual Studio 2022 to create a solution named Lab3. Within this solution, you will create multiple projects, each corresponding to a specific task. For each task, you will create a project (with the same name as the task) and add a .cpp file in the project. This .cpp file will contain the main function for the project. As discussed and demonstrated in the in-person class, you will follow these steps to ensure a structured solution with individual projects, each demonstrating your ability to organize and implement code for different tasks effectively. Follow the instructions given below to create a new solution and projects within this solution.

## Instructions for creating solution and projects

## Create a New Solution

1. Open Microsoft Visual Studio 2022\.  
2. In the Create a new project dialog, select Empty Project.  
3. Click Next.  
4. Uncheck the check box: "Place solution and project in the same directory".  
5. For the Project name, type `Task1`.  
6. Enter `Lab3` as the Solution name.  
7. Choose a location to save the solution. This should be: "C:\\Users\<yourusername\>\\PRG210\\Labs"  
8. Click Create. This will create the solution and project for the first task.  
9. For any subsequent tasks, follow the steps in \#2. below.

## Create Projects for Each Task

* Right-click on the `Lab3` solution in the Solution Explorer.  
* Select Add, then click on New Project.  
* In the Create a new project dialog, select Empty Project.  
* Click Next.  
* Enter the task name as the Project name.  
* Ensure the Location is within the `Lab3` solution folder.  
* Click Create.  
* Repeat these steps for each task, ensuring each project name matches the corresponding task name.

## Add Main Function File

* For each project, right-click on the Source Files folder in the Solution Explorer.  
* Select Add, then click on New Item.  
* In the Add New Item dialog, select C++ File (.cpp).  
* Enter the task name as the Name of the .cpp file.  
* Click Add.  
* Write the main function in this .cpp file.

## Instructions for Lab submission

* Take screenshots wherever required.  
* Name the screenshots as the project name (task1.jpg, task2.jpg, etc)  
* Add the screenshots in a word document in the correct order.  
* Export the word document as pdf. Name the PDF as StudentName\_Lab3.pdf.  
* Submit the pdf on Blackboard.  
* The following deductions apply:  
* Incorrect screenshot names: \-20% of overall grade.  
* Incorrect document name: \-20% of overall grade.  
* Missing username in the terminal: \-100%

# INVESTIGATION 1: Pointers

Pointers are variables that store the memory address of another variable. A pointer is declared using the \* symbol. It is initialized with the address of a variable using the & operator. 
```cpp 
int var = 10;  
int *ptr = &var; // ptr now holds the address of var
``` 

**Dereferencing:**
 
Dereferencing a pointer (using \*) accesses the value stored at the address the pointer points to.
```cpp  
cout << *ptr; // Outputs the value of var
```
## Task 1

* Project Name: `Task1`  
* Main File Name: `task1.cpp`  
* In the `task1.cpp` file, write the code to:  
  * Declare a double variable named `ted` and initialize it to `42.24`.  
  * Declare a pointer named `ptr` and assign it the address of `ted`.  
  * Display the value of `ted` using the pointer (dereference the pointer).  
  * Display the address of `ted` using the pointer.  
* Save the project.  
* Build the solution.  
* Run the `task1.exe` file from the terminal.  
* Take a screenshot of the code and terminal. Make sure the terminal shows your username.

## Task2

* Project name: `Task2`  
* Main file name: `task2.cpp`  
* Copy the following code to `task2.cpp`:  
```cpp
  #include <iostream>  
  using namespace std;  
  int main() {  
  	// 1. initialize two int variable i and i2 with the value of 10 and 42 respectively  
  	// 2. initialize and declare a pointer ip with the address of i  
  	cout << "The address of ip is " << ip << endl;  
  	// 3. update the pointer ip with the address of i2  
  	cout << "The new address of ip is " << ip << endl;
   return 0; 
  }  
  ```
* Complete above code to complete 3 items mentioned.  
* Save the project.  
* Build the solution.  
* Run the `task2.exe` from terminal.  
* Take screenshot of code and terminal. Make sure the terminal shows your username.

# INVESTIGATION 2: Dynamic Memory Allocation 

Dynamic memory allocation allows a program to allocate memory at runtime rather than at compile time. In C++, dynamic memory is managed using the `new` and `delete` operators. Dynamically allocated memory resides in the heap, separate from the stack memory used for local variables. Please note that if you use `new` operator to allocate memoery for a variable, you must use `delete` operator to delete that memory when you no longer need that variable.
```cpp
int *ptr = new int(10); // Allocates memory for one integer and initializes it to value 10  (it is NOT an array of size 10)
cout << *ptr << endl;   // Outputs: 10  
delete ptr;             // Frees the allocated memory
```
## Task 3

* Project Name: `Task3`  
* Main File Name: `task3.cpp`
* Copy the following code to `task3.cpp`:  
```cpp
  #include <iostream>  
  using namespace std;  
  int main() {
  	// 1. Declare book information variables  
  	// 2. Allocate memeory to above variables
  	// 3. Store values in the variables
  	// 4. Print the information
  	// 5. Free the dynamcially allocated memoery
 
   return 0;  
  }  
  ```
* In the `task3.cpp` file, write the code to store information about a book, where each book has a unique integer ID, a floating-point rating, and an character to store initial of the author's first name:  
  * Dynamically allocate memory for the integer (`bookID`), a float (`bookRating`), and a character (`authorInitial`).  
  * Assign values to these pointers: `101` for the book ID, `4.5` for the rating, and `'A'` for the author's initial.  
  * Print the details of the book using the pointers.  
  * Release the memory allocated for all pointers.  
* Save the project.  
* Build the solution.  
* Run the `task3.exe` file from the terminal.  
* Take a screenshot of the code and terminal. Make sure the terminal shows your username.

# INVESTIGATION 3: nullptr keyword in C++

The `nullptr` keyword in C++ represents a null pointer constant. It was introduced in C++11 to provide a safer and more explicit way to represent a pointer that does not point to any valid memory location.

## Task 4

* Project Name: `Task4`  
* Main File Name: `task4.cpp`  
* This task will help you understand the behavior of a pointer when memory is dynamically allocated, freed, and reset to nullptr. You will also explore what happens when you attempt to delete a pointer twice, and why resetting it to nullptr is important.  
* Copy the following code to `task4.cpp`and complete the code by filling in the TODO sections:  
```cpp
  #include <iostream>  
  using namespace std;  
    
  int main()  
  {  
      int num = 42;  
      int *ptr = &num; // TODO: change this code and Dynamically allocate memory and save its address in ptr variable
      cout << "Pointer value after allocation: " << ptr << endl;  
    
      // TODO: Free the allocated memory  
      cout << "Pointer value after deletion: " << ptr << endl;  
    
      // TODO: Reset pointer to nullptr  
      cout << "Pointer value after resetting to nullptr: " << ptr << endl;  
    
      // TODO: Call delete again on the ptr (nullptr)  
      cout << "Pointer value after deleting nullptr: " << ptr << endl;  
    
      cout << "End of program." << endl;  
    
      return 0;  
  }  
  ```
* What is the behavior of the program when you comment out the "Reset pointer to nullptr" step? Why does this happen?  
* Save the project.  
* Build the solution.  
* Run the `task4.exe` file from the terminal.  
* Take a screenshot of the code and terminal. Make sure the terminal shows your username.

## Task 5

* Project Name: `Task5`  
* Main File Name: `task5.cpp`  
* Copy the following code in the file `task5.cpp`.
```cpp
  #include <iostream>  
  using namespace std;  
    
  int main()  
  {  
      int *primaryPtr = new int(100);  
      cout << "Primary pointer value: " << *primaryPtr << endl;  
    
      int *secondary = primaryPtr;  
      cout << "Secondary pointer value: " << *secondary << endl;  
    
      delete primaryPtr;  
      cout << "Memory freed by Primary pointer." << endl;  
    
      cout << "Secondary pointer value after Primary deletes memory: " << *secondary << endl;  
    
      return 0;  
  }  
  ```
* Fix the code by checking the validity of `primaryPtr` before accessing the secondary pointer.  
* Save the project.  
* Build the solution.  
* Run the `task5.exe` file from the terminal.  
* Take a screenshot of the code and terminal. Make sure the terminal shows your username.

# INVESTIGATION 4: Dynamic Arrays

Dynamic arrays are arrays whose size can be determined at runtime. Unlike static arrays, which have a fixed size determined at compile time, dynamic arrays allow flexibility in managing memory, making them particularly useful when the required size of an array is not known in advance.

**Syntax:**  
```cpp
int size = 5;  
int *arr = new int[size]; // Allocates memory for an array of 5 integers
```
**Assigning Values:**
```cpp
for (int i = 0; i < size; i++) {  
    arr[i] = i + 1; // Assign values to the array  
}
```
**Freeing Memory:**  
```cpp
delete[] arr; // Frees the memory allocated for the array  
arr = nullptr; // Avoid dangling pointers
```
**Initializing value at compile time:**  
```cpp 
int *arr = new int[3]{1, 2, 3};
```
## Task 6

* Project Name: `Task6`  
* Main File Name: `task6.cpp`  
* Create the file `task6.cpp` and do the following:
  * Add necessary include files, using statements and skeleton of main function, complete the main function to achieve the following
  * Prompt the user to input the number of students in a class and save this input in the `size` variable.  
  * Dynamically allocate a float array that will have `size` number of elements.  
  * Use a loop to allow the user to enter scores for each student and save it in corresponding location of the array.  
  * Display all scores using another loop.  
  * Calculate and display the average score.  
  * Free the memory allocated for the dynamic array using delete[].  
* Save the project.  
* Build the solution.  
* Run the `task6.exe` file from the terminal.  
* Take a screenshot of the code and terminal. Make sure the terminal shows your username.

## Task 7

- Project Name: `Task7`
- Main File Name: `task7.cpp`
- Open the file `task7.cpp` and copy the following code:  
  ```cpp
  #include <iostream>  
  using namespace std;  
    
  int main()  
  {  
      int size1 = 3, size2 = 2;  
      int *array1 = // TODO: Dynamically allocate and initialize the first array for size1 number of elements
      int *array2 = // TODO: Dynamically allocate and initialize the second array for size2 number of elements
      int *mergedArray = // TODO: Dynamically allocate memory for the merged array that will have size1+size2 number of elements
      for (int i = 0; i < size1; i++)  
      {  
      // TODO: Copy elements from the first array into the merged array  
      }  

      for (int i = 0; i < size2; i++)  
      {  
          // TODO: Copy elements from the second array into the merged array (you must not over-write already copied data in merged array)
      }  
    
      cout << "\nMerged Array:" << endl;  
      for (int i = 0; i < size1 + size2; i++)  
      {  
          cout << "Element " << i + 1 << ": " << mergedArray[i] << endl;  
      }  
    
      // TODO: Free the memory allocated for all arrays  
    
      return 0;  
  }
  ```
- Complete all TODO’s.
- Save the project.
- Build the solution.
- Run the `task7.exe` file from the terminal.
- Take a screenshot of the code and terminal. Make sure the terminal shows your username.

## Task 8

- Project Name: `Task8`
- Main File Name: `task8.cpp`
- Open the file `task8.cpp` and copy the following code:  
  ```cpp
  #include <iostream>  
  using namespace std;  
    
  int main()  
  {  
      char firstName[50];
      char lastName[50];
  
      // TODO 1: Ask user for first name and save in firstName

      // TODO 2: Ask user for last name and save in lastName
  
      // TODO 3: Declare a character pointer variable called 'fullName' and dynamicaly allocate it memory equal the sum of lenghts of firstName and lastName + 2 (use strlen() function to get lenghts)
          // +2 above: one for space between first and last names and second for null character at the end

      // TODO 4: Use a for loop to copy each character of firstName in fullName
      // TODO 5: Add a space in fullName after firstName
      // TODO 6: after sapace copy all chars of lastName in fullName (again use a for loop to do that)
      // TODO 7: Add a null character ('\0') as last element of fullName

      // TODO 8: print fullName

      // TODO 9: deallocate fullName
    
      return 0;  
  }
  ```
- Complete all TODO’s.
- Save the project.
- Build the solution.
- Run the `task8.exe` file from the terminal.
- Take a screenshot of the code and terminal. Make sure the terminal shows your username.
  
# INVESTIGATION 5:  References in C++

A reference in C++ is an alias for an existing variable. It provides a way to access and modify the original variable using an alternative name. A reference does not have its own memory address. It shares the same memory location as the variable it references. It must be initialized at the time of declaration and cannot be reassigned to reference another variable later. Deceleration of a reference variable is similar to a pointer variable declaration but it uses & instead of *. A reference to a variable is just another name for same variable

**Declaration and Initialization:**
```cpp
int var = 42;  
int &ref = var; // 'ref' is a reference to 'var'
```
## Task 9

* Project Name: `Task9`  
* Main File Name: `task9.cpp`  
* Open the file `task9.cpp` and do the following:  
  * Declare and initialize an integer variable `var`  
  * Create a reference `ref` to the variable `var`  
  * Create a pointer `refPtr` to the reference `ref`  
  * Display the value, address, and size of the variable  
  * Display the value, address, and size of the reference  
  * Display the value, dereferenced value, and size of the pointer  
* Save the project.  
* Build the solution.  
* Run the `task9.exe` file from the terminal.  
* Take a screenshot of the code and terminal. Make sure the terminal shows your username.

