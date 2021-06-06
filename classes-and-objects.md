# Classes & Objects

Custom Data Types for Programs, essentially creating a 'Model' of an object. There's int for number, string for words, but what about, say a 'student' data type in a school management software. That requires its own set of data fields, unique to student. Enter the Class.

## Class

Class is a specification of a new data type with attributes (strings, bools, etc.)

- Student Class
  - name (string)
  - gpa (double)
  - year (int)
  - hasScholarship (bool)
  - hasHonors() (func)
  - giveScholarship() (func)

When creating the class, you are defining it (similar to declaring a function without the body). Not creating one. No student is created. To do that you create an Object.

## Declaring a class

```c++
class Song {

};
```

## Class Members

Components of a class are called class members. Just like you can get a string’s length using .length(), you can access class members using the dot operator (object.class_member).

- Attributes - member data, consist of information about an instance of the class
- Methods - member functions, are functions that you can use with an instance of the class. We use a . before method names to distinguish them from regular functions

We *encapsulate* — or enclose for simpler user access — attributes and methods in a class like this:

```c++
class City {

  // attribute
  int population;
  
 // public will be explained later
 public:
  // method
  void add_resident() {
    population++;
  }
}
```
Unless we have a mostly empty class, it’s common to split function declarations from definitions. We declare methods inside the class (in a header), then define the methods outside the class (in a .cpp file of the same name).

How can we define methods outside a class? We can do this using ClassName:: before the method name to indicate its class like this:

```c++
// inside city.cpp
int City::get_population() {
  return population;
}
```
Unlike with regular functions, we need to include the header file in the .cpp file where we define the methods.

**Note:** We must declare a method inside the class if we want to define it outside.

### Example:

```c++
// song.hpp declarations
class Song {
  std::string title;

public:
  void add_title(std::string new_title);
  std::string get_title();
};
```

```c++
// song.cpp definitions of the member functions
void Song::add_title(std::string new_title) {
  title = new_title;
};

std::string Song::get_title() {
  return title;
};
```

## Creating Objects

an object is an instance of a class, which encapsulates data and functionality pertaining to that data

```c++
// music.cpp (int main file)
// instantiate the Song class
Song electric_relaxation;

// using built in method, add a title
electric_relaxation.add_title("Electric Relaxation");

// using built in method, get title and output to terminal
std::cout << electric_relaxation.get_title() << "\n";
};
```

## Public vs Private

By default, everything in a class is `private`, meaning class members are limited to the scope of the class. This makes it easier to keep data from mistakenly being altered, and abstracts away all the nitty gritty details. If you try to access a private class member, you’ll get an error:

  `error: 'population' is a private member of 'City'`

But sometimes you need access to class members, and for that, there is `public`. You can use it to make everything below accessible outside the class:

```c++
class City {
 
  int population; 
 
public: // stuff below is public
  void add_resident() { 
    population++;
  }
 
};
```

There is also a `private` access modifier for when you want something below `public` to be private to the class:

```c++
class City {
 
  int population; 
 
public:
  void add_resident() { 
    population++;
  }
 
private: // this stuff is private
  bool is_capital;
 
};
```

## Constructors


