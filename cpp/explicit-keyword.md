# `explicit` keyword in c++
### date: 2021-01-31

* `explicit` prohibits implicit conversion of a variable to a Queue class 
i.e., all Queue objects must be constructed manually and explicitly.

```cpp
#include <iostream> 
  
using namespace std; 
  
class Complex 
{ 
private: 
    double real; 
    double imag; 
  
public: 
    // Default constructor 
    Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {} 
  
    // A method to compare two Complex numbers 
    bool operator == (Complex rhs) { 
       return (real == rhs.real && imag == rhs.imag)? true : false; 
    } 
}; 
  
int main() 
{ 
    // a Complex object 
    Complex com1(3.0, 0.0); 
  
    if (com1 == 3.0) 
       cout << "Same"; 
    else
       cout << "Not Same"; 
     return 0; 
} 
```

* The code above, when compiled, will output the below.

```sh
Same
```

* This is because the comparison of the instance of the Complex class and 
a variable led to implicit type conversion of the variable to an instance of
the class automatically (as long as the default constructor function is 
defined for one variable)

* You can prevent this from happening by using the `explicit` keyword. The code 
below will result in a compiliation error.

```cpp
#include <iostream> 
  
using namespace std; 
  
class Complex 
{ 
private: 
    double real; 
    double imag; 
  
public: 
    // Default constructor 
    explicit Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {} 
  
    // A method to compare two Complex numbers 
    bool operator== (Complex rhs) { 
       return (real == rhs.real && imag == rhs.imag)? true : false; 
    } 
}; 
  
int main() 
{ 
    // a Complex object 
    Complex com1(3.0, 0.0); 
  
    if (com1 == 3.0) 
       cout << "Same"; 
    else
       cout << "Not Same"; 
     return 0; 
} 
```
