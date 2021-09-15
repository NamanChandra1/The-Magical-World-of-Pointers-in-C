## **The ‘&’ and ‘*” operators**

Consider the below declaration

```c
int a = 5;
```

**How does the C Complier sees it :**
     a → Location Name/ Variable Name
     5 → Value at location/ Value at Address
    1476 → Location number/ Address of Variable

**The ‘&’ operator is C’s ‘address of’ operator.**
• The expression &a returns the address of variable a, which in this case happens to be 1476

%u - Format specifier used for unsigned integer. C Complier returns the unsigned integer value for this address hence we use this format specifier

```c
/* Program 1*/
#include<stdio.h>
int main()
{
int a = 5;
printf (“Address of a = %u\n”, &a);
printf (“Value of a = %d \n”, a);
return 0;
}

//Output:
Address of a = 1476
Value of a = 5
```

The ‘*’ operator is called the ‘Value at Address’ operator and returns the value stored at a particular address.

- &a gives the address of variable a
- *(&a) gives the Value stored at that Address

```c
/* Program 2*/
#include<stdio.h>
int main()
{
int a = 5;
printf (“Address of a = %u\n”, &a);
printf (“Value of a = %d \n”, a);
printf (“Value of a = %d \n”, *(&a));
return 0;
}

//Output

Address of a = 1476
Value of a = 5
Value of a = 5
```

## POINTERS EXPLAINED

• Let us allocate a variable to collect this address

> b = &a ;

- b is a special variable as it contains address of another variable
- This special variable must be declared as follows

> int *b ;

- The declaration tells the compiler that b would be used to store the address of an integer variable – in other words, **b points to an integer**
- As we now know, the ‘*” symbol stands for ‘Value at address’; Thus  int *b means the value at the address stored in b is an integer, in this case the value at address 1476 is 5 if we print *b in our program.



```c
/* Program 3*/
#include<stdio.h>
int main()
{
int a = 5;
int *b;
b=&a;
printf (“Address of a = %u\n”, &a);
printf (“Address of a = %u\n”, b);
printf (“Address of b = %u\n”, &b);
printf (“Value of b = %d\n”, b);
printf (“Value of a = %d\n”, a);
printf (“Value of a = %d\n”, *(&a));
printf (“Value of a = %d\n”, *b);
return 0;
}

```

```c
// Output :
Address contained in intpoint = 2342
Address contained in charpoint = 9843
Address contained in floatpoint = 3432
Value of a = 5
Value of b = A
Value of c = 9.980000
```

- Here we have used 3 different pointer variables to point to three different format types. Integer pointer stores the address of the integer variable , float pointer stores the address of a float variable and character pointer stores the address of a character variable
- In reality, for each of the format type the compiler allocates memory
to the variable. For e.g., for integer variable ‘a’ occupies 4 bytes of
memory
- The statement intpointer = &a stores only the first byte in the pointer
variable intpointer.
- The address of the first byte is often known as the base address
- If you wish to access an integer value stored in a variable storing its
address, it is necessary that the address be stored in an integer
pointer. Thus, we need to be careful that we are using the same
format specifiers for the variable and the respective pointer.

## Passing Address to Functions

(Call by Value vs Call by Reference)

The Arguments are generally passed to functions in 2 ways :
1. Sending the value of the arguments (Call by Value)
2. Sending the address/ reference of the arguments (Call by reference)

- Call by Value
• In this method of passing the arguments – the value of each actual argument in is copied into corresponding formal argument of the called function.
• The changes made to the formal arguments in the called function have no effect on the values of the actual arguments in the calling function
• Let us look at this in more detail with the
help of an example

```c
/* Program 5*/
#include<stdio.h>
void swapnum(int, int); //function prototype
int main()
{
int a =5; int b =10;
swapnum(a,b); //function call
printf (“Numbers a=%d and b =%d\n”, a, b);
return 0;
}
void swapnum(int x, int y);
{
int temp;
temp = x;
x = y;
y = temp;
printf(“Numbers x=%d and y=%d\n”, x ,y);
}
```

```c
Output :
Numbers x=10 and y=5
Numbers a=5 and b=10
```

- Two separate variables x and y get created in the swapnum() function
- Here as you can see the values of variables a and b gets copied to variable x and y.
- The values of a and b remain unchanged even after we swap the values of x and y.

- Call by Reference
• In this method of passing the arguments –the address of each actual argument of the calling function in is copied into corresponding formal argument of the called function.
• By using the formal arguments in the called function we can make changes in the actual arguments of the calling function.
• Let us look at this in more detail with the
help of an example

```c
/* Program 6*/
#include<stdio.h>
void swapnum(int *, int *); //function prototype
int main()
{
int a =5; int b =10;
swapnum(&a,&b); //function call
printf (“Numbers a=%d and b =%d\n”, a, b);
return 0;
}
void swapnum(int *x, int *y);
{
int temp;
temp =*x;
*x = *y;
*y = temp;
}
```

```c
Output :
Numbers a=10 and b=5
```

Two separate integer pointer variables x and y get created in the swapnum() function
• Here as you can see the address of variables a and b gets copied to pointer variables x and y.
• The values of a and b are changed in the called function by use of pointers

## FUNCTIONS RETURNING POINTERS

• Similar to the way functions return different data types like int, float,
double, etc. , function can also return a pointer
• To make function return a pointer it has to be explicitly mentioned in the prototype declaration as well as in function definition
• In the example it shows that printfun() is a function which received nothing but returns an integer pointer.
• The printf() would print the address contained in p (address of variable a)

```c
/* Program 7*/
#include<stdio.h>
int *pointfun(); //function prototype
int main() {
int *p;
p = printfun();
printf(“Address is %u”, p);
return 0;
}
int *printfun() //function definition
{
int a;
return (&a);
}
```

```c
Output:
Address is 2345
```
