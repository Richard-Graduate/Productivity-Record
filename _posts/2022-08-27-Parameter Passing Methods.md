---
title: "Parameter Passing Methods"
categories:
  - C++ Concepts
tags:
  - C++ Concepts
---
## Parameter Passing Methods

### Call By Value 
```cpp
int add(int a,int b)
{
    int c;
    c=a+b;
    return c;
}
int main()
{
    int num1=10,num2=15,sum;
    sum=add(num1+num2);
    return 0;
}
```
Values are passed here and this type of parameter pasing, if any changes are done to  

this formal parameters   {**int add(int a,int b)**},   

that will not change actual parameters{**num1+num2**}.  


### Call By Address 
The sytax of **call by address**,the parameter should be of type pointers.
```cpp
void swap(int *x,int *y)
{
    int temp;
    temp=*x;
    *x=*y;
    *y=temp;
}
```
We purpose the address of actual parameters.So these pointers will be indirectly accessing these values itself.
```cpp
int main()
{
    int num1=10,num2=15;

    swap(&num1,&num2);

    sum=add(num1+num2);
    cout<<"First Number"<<num1;
    cout<<"Second Number"<<num1;

    return 0;
}
```  


```markdown
First Number 15
Second Number 10
``` 
This function is modifying actual parameters.  
So it is not returning anything.  
You can see that swap function is modifying **two variables** number one and number two.  
But a function can return **only one value**.
So better use call by address.


### Call By Reference
```cpp
void swap(int &x,int &y)
{
    int temp;
    temp=x;
    x=y;
    y=temp;
}
```
The concept of references, it is a nickname of a variable,
so **x means num1**.
```cpp
int main()
{
    int num1=10,num2=15;

    swap(num1,num2);

    sum=add(num1+num2);
    cout<<"First Number"<<num1;
    cout<<"Second Number"<<num1;

    return 0;
}
```  
There are two possibilities that a compiler can convert its function as an inline function and copy the entire code to **main()**.
Or it can make these as pointers also.
