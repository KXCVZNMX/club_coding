# Lesson 3: An introduction to data types in C++

A data type is something that stores a value. In C++, or any languages, there are three major types of data types: primitive, complex, and user-defined. In this lesson, we will be discussing the primitive and complex data types. User-defined data types would be discussed later, as it includes `class`es and `struct`s.

## Primitive Data Types
Primitive data types in C++ includes data types to store integers (`short`, `int`, `long`, `long long`, etc.), decimals (`float`, `double`, `long double`), characters (`char`, etc.), `bool` (true or false).

For all data types of C++, visit the [C Data Types](https://en.wikipedia.org/wiki/C_data_types) page on Wikipedia.

Examples of how to use these data types are as shown:

### Integers
```cpp
int x; 
```
This is an uninitialised integer, although no value were assigned, but there is a default value. Hence, when you want to have a value as 0, initialise it as 0, as such:

```cpp
int x = 0;
```

An `int` could store values from -2^31-1 to 2^31-1. 

```cpp
int x = 2147483647 + 1;
```

You may think here that `x` equals to 2147483648, but instead, it equals -2147483647. This is due to overflowing, as the number exceeded the size assigned to `x`.

To store even larger numbers, use the `long` (-2^63-1 to 2^63-1), and `long long` (depending on system, potentially the same as `long`). If you do not want to store negative numbers, you can add an `unsigned` to `int` or `long`, to make the have the range of 0 to 2^16-1 and 0 to 2^63-1 respectively.

### Characters
```cpp
char x = 'a'
```
To define a character, use `char`, and assign a value with it. Note that it has to be using a single quotation mark, because the double quotation marks are only used for `string`s and `const char*` (we will talk about this a few lessons later).

```cpp
char x = 97
```
C++ allows implicit conversion from integers to characters through using the ASCII conversion. 97 here is the same as "a" in ASCII. Char has a range of -128 to 127.

### Boolean
```cpp
bool x = true;
``` 
`bool` is an interesting data type, as it takes exactly 1 bit. as seen above, it says `true`, whereby, the opposite is `false`. `true` and `false` here are really just a `#define` of 1 and 0, hence this is possible as well:
```cpp
bool x = 1; // x = true
```

## Complex Data Types
There are 3 major data types used in C++, which are `array`, `vector`, `string`.

### Array and Vector
`array`s and `vector`s are both lists, where it stores a list of whatever data types the user provides. For example, a list of 1 to 5. 

Note: `vector` is found in the `<vector>` library, so you have to `#include` it before use.

```cpp
// initialisation
int l[5] = {1, 2, 3, 4, 5};
std::vector<int> v = {1, 2, 3, 4, 5};
```
Although here, both `l` and `v` contains the same information of a list of numbers from 1 - 5. The major difference between an array and a vector is that vector is sizable, it is dynamic. Arrays have a fixed size upon initialisation. For example, here, the array has a size of 5, and it could not be changed. Vectors, on the other hand, is dynamic, and allows operation such as `push_back` (append an element into the end of the list), and other operations that could be dealt to a list.
```cpp
std::vector<int> v = {1, 2, 3, 4, 5};
v.push_back(6);
// v == {1, 2, 3, 4, 5, 6} now
```

### Strings
Strings in C++ is similar to a "wrapper" class, as string is simply a pointer to an array of characters (we will be diving into pointers later).

Strings have similar functions to vectors, including `push_back`, `contains`, `find`, etc.
```cpp
// initialisation
std::string s = "Hello, World!";
```

### Indexing into Array, Vector, and Strings

All these of these complex data structures have the same indexing method, `[x]`, where x is the index of the element you want to access. Although, use indexing carefully, there is a possibility of `index out of bound`, which is a fatal error for the program (as it is accessing a non-existent thing). The range you can index is from 0 to the length of your data structure (obtained from `x.length()`);
