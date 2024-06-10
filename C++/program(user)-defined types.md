# What are program-defined types?
There are hundreds of other potentially useful types that C++ doesn’t include because it’s just not possible to anticipate everything that someone might need. Instead, **C++ solves such problems by allowing us to create entirely new custom types**. these types types are called user/program-defined types. C++ has two categories of compound types that allow for this: the enumerated types and the class types.
# Defining program-defined types
Program-defined types must be defined before they can be used. The definition for a program-defined type is called a **type definition.** 
###### Example of a program-defined type
```C++
struct Fraction {
	int numerator {};
	int denominator {};
};

int main() {
	Fraction f{ 3, 4 };
	return EXIT_SUCCESS;
}
```

> [!NOTE] Naming a program-defined type
> Name your program-defined types starting with a capital letter and do not use a suffix!
> (e.g. **==Fraction==**, not ==fraction==, ==fraction_t==, or ==Fraction_t==)
# Using program-defined types throughout a multi-file program
A program-defined type used in only one code file should be defined in that code file as close to the first point of use as possible.

A program-defined type used in multiple code files should be defined in a header file with the same name as the program-defined type and then `#included` into each code file as needed.

###### Example of what the Fraction type would look like if moved to a header file (Fraction.h):
```c++
#ifndef FRACTION_H
#define FRACTION_H

// Define a new type named Fraction
struct Fraction {
	int numerator {};
	int denominator {};
};

#endif
```
###### Using the Fraction.h header (Fraction.cpp):
```c++
#include "Fraction.h"

int main() {
	Fraction f{ 3, 4 };
	return EXIT_SUCCESS;
}
```
