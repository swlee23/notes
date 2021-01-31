# 'explicit' keyword in C++
### date: 2021-01-31

* The `delete` operator deallocates memory and calls the destructor for a 
single object created with new. 

* The 'delete []' operator deallocates memory and calls destructors for an
array of objects created with 'new []'

* Using 'delete' on a pointer returned by 'new []' or 'delete []' on a pointer
returned by new results in undefined behavior.
