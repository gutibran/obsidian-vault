# 1.2: Programs
- C++ is compiled
- Source code is processed by the compiler which produces object files which are combined by the linker which finally produces an executable.
- The source code of the programs is portable meaning the source code can be compiled on a variety of system but not the executables themselves are not portable
- The two entities in ISO C++ standards define core language features and standard library components
- The standard library components are written in C++ and is provided by every C++ implementation
- Statically typed meaning the type of every entity/object must be known to the compiler at its point of use
- The type of an object determines the set of operations that can be performed and its layout in memory

- `int main() {}` must be in every program. The program starts by executing `main()` and returns a integer value to the system when it is finished. If no value is returned then the program has run successfully, any nonzero return value indicates failure. Linux and Unix based OS's make use of the return value, Windows usually does not.

Here is `hello_world.cpp`. `import` (new to C++ 20 and presents the entire standard library as a single module) declarations tell the compiler to make declarations of the standard library available. `<<` is the "put to" operator writes the operand to the left onto the first operand.
```c++
#include <iostream>
//import std;

int main() {
	std::cout << "Hello, world!\n";
}
```

## 1.3: Functions
Functions specify how an operation is to be done. Functions are given a name, a return type, and arguments and their respective argument types. Argument types are checked and implicitly type conversion takes place if necessary.

```c++
returnType functionName(arg1Type arg1Name)
{
	// do something
}
```

Function declarations do not have to have their arguments named.
```c++
returnType functionName(arg1Type);
```

