# Output

## Basic .cpp File Setup

```C++
// libraries that are required for program to run
#include <iostream>

int main() {
  // std::cout is the character output stream, spoken c-out (how you output to the terminal)
  // << is an operator
  // "" & ; double quotes and semi-colon required
  std::cout << "Codecademy\n";
}
```

```C++
#include <iostream>

int main() 
{
  std::cout << "       1\n";
  std::cout << "     2 3\n";
  std::cout << "   4 5 6\n";
  std::cout << "7 8 9 10\n";        
}
```

### Illustration using Hello, World

```C++
// This program outputs the message "Hello World!" to the monitor

// The 'pre-processor directive' > iostream is a library that allows for input and output
#include <iostream>
 
// all C++ programs must have a function called main()
int main() {
   std::cout << "Hello World!\n";
   
   // optional, but good practice. 0 indicates successful code run
   return 0;
}
```

## Compiling
- Code — writing the program
- Save — saving the program
- Compile — compiling via the terminal
- Execute — executing via the terminal

### Compiler

`g++ hello.cpp` • translates the C++ you wrote into machine code
- this creates an output file `a.out`, then that can be run in terminal to execute the machine code

```unix
$ g++ hello.cpp 
$ ./a.out 
Hello World!
```
**To Name the output file:** `g++ hello.cpp -o hello` then you would run `./hello`

## The Process

 C++ source code files are given the suffix:

- .cpp (ex: hello.cpp) or
- .h (ex: std_lib_facilities.h).

Typically![JUDOhEj](https://user-images.githubusercontent.com/26289436/116697093-c1fe8600-a990-11eb-8eb8-c9b937241d8f.png)


