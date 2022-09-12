---
title: "Structure  as Parameter"
categories:
  - C++ Concepts
tags:
  - C++ Concepts
---
## Parameter Passing Methods

### Call By Value 
```cpp
struct Rectangle
{
    int length;
    int breadth;
};

void fun(struct Rectangle r)
{
    r.length=20;
    cout<<"Length"<<r.length<<endl<<"Breadth"<<r.breadth<<endl;
}
```
```cpp
int main()
{
    struct Rectangle r={10,5};
    fun(r);
    printf("Length %d \nBreadth %d\n,r.length,r.breadth") ;
}
```
We use **dot operator** for accessing the members and here this is called the value and this is also **variable**.  

### Call By Address  

Now in **called address** from here we will pass the address of a rectangle.
```cpp
struct Rectangle
{
    int length;
    int breadth;
};

void fun(struct Rectangle *r)
{
    r->length=20;
    cout<<"Length"<<r->length<<endl<<"Breadth"<<r->breadth<<endl;
}
```
```cpp
int main()
{
    struct Rectangle r={10,5};
    fun(&r);
    printf("Length %d \nBreadth %d\n,r.length,r.breadth") ;
}
```
```md
Length20
Breadth5
Length 20
Breadth 5
```  
### Returning the Address of Structure

```cpp
struct Rectangle
{
    int length;
    int breadth;
};

void fun(struct Rectangle r)
{
    struct Rectangle *p;
    p=new Rectangle;
    //p=(struct Rectangle *)malloc(sizeof(struct Rectangle));
    p->length=15;
    p->breadth=7;

    return p;
}
```
So this is structure object is created in **Heap** and its address is written by this function inside.
```cpp
int main()
{
    struct Rectangle *ptr=fun();  

    cout<<"Length"<<ptr->length<<endl<<"Breadth"<<ptr->breadth<<endl;

    return 0;
}
```
```md
Length 15
Breadth 7
```  
So this program is demonstrating how function can return a **pointer** to an object created in a heap,  
 and that can be accessed using **main function** also it can be accessed by any function of that point.








