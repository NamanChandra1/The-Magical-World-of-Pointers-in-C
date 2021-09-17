## ACCESSING ARRAY ELEMENTS USING POINTERS

An ARRAY is a collection of similar elements. Also known as subscripted variable

- Examples of Array declaration
    - int a[30];  → Array is of type integer and of size 30
    - float b[50]; → Array is of type float and of size 50
    - char ch[1 2]; → Array is of the type character and of size 12
- Elements of arrays are always stored in a contiguous memory location. The first element in the array is numbered 0 and the last element is size of array -1. Thus, for an array - int a[30] the first element is a[0] and Iast element is a[29]
- Array can be initialized at the same place that it is declared.

E.g. int a[3] = {11,22,33);  int b[] = {2, 4, 5};

A good programming practice is ensure that the subscript used for an array does not exceed the size of the array. Data entered with a subscript exceeding the array size will lead to unpredictable results

The following operations can be performed on a pointer

1. Addition of a number to a pointer
2. Subtraction of a number from a pointer
3. Subtraction of one pointer from another
4. Comparison of 2 pointer variables

```c
/*Program 8*/
#include<stdio.h>
int main()
{
int a[3] = {11, 23, 45};
int *b;
int i;
b = &a[0];
for (i=0; i<=2; i++){
printf("The number is %d\n and address is %u",*b,b);
b++;// increments pointer to point to next location 
}
return 0;
}
```

```c
Output:
The number is 11 and address is 2456
The number is 23 and address is 2460
The number is 45 and address is 2464
```

```c
/* Program 9*/
#include<stdio.h>
int main()
{
int al = {11, 23, 45};
int *b, *c;
b = &a[0];
c = &a[2];
printf("c-b is %d\n", c-b);
if (c==b)
	printf" pointers pointing to same loc \n");
else
	printf" pointers pointing to different loc \n");
return 0;
}
```

```c
Output
c-b is 2
pointers pointing to different loc
```

- b and c have been declared as integer pointers and are holding addresses of 0th and 2nd element of the array
- The expression c-b will print the value as 2, as b and c are pointing to memory locations that are 2 integers apart and as we know elements of arrays are stored in contiguous memory location
- Also we can compare pointers by using the == operator. In this example the comparison is FALSE and hence we get the said output

## PASSING ARRAY TO A FUNCTION

- The address of the 0th element and the number of elements in the array is being passed to show1() and show2() functions.
- The address of the 0th element (or the base address) can be passed in 2 ways
• show1(&a[0], 3);
• show1(a,3) ; → Array name itself acts as a pointer to 1st element of the array
- In the show1() function the address is accepted in the variable int *b and in show2() function the address is accepted in int b[ ].
• In show2() function, even though b is still an integer pointer, the array notation gives us ease of access by using the notation b[c] to access the array elements.

```c
/* Program 10*/
#include<stdio.h>
void show1( int *, int); // one way of function prototype
void show2( int [ ], int); // other way of function prototype
int main()
{
int a[3] = {11, 23, 45};
show1( &a[0], 3); printf(“\n”);
show2( &a[0], 3); printf(“\n”);
show1(a,3); //array name as address of 1st element of array
return 0;
}
void show1 ( int *b, int n)
{
int c;
for ( c = 0 ; c<=n; c++)
{
printf(“element =%d ::”, *b);
b++; // pointer incremented to point to next element
}
}
void show2 ( int b[ ], int n)
{
int c;
for ( c = 0 ; c<=n; c++)
printf(“element =%d ::”, b[c]);
}
```

```c
Output:
element =11 :: element =23 :: element =45
element =11 :: element =23 :: element =45
element =11 :: element =23 :: element =45
```

• In the previous program please refer to the array,
• int a[3] = {11, 23, 45};

• By mentioning the name of the array we get address of the 0th element/ base location of the array

• So, *a will give the value at the 0th element of the array i.e. 11.
• *a can be written as *(a+0). Similarly *(a+1) will give the value at the 1st element of the array i.e. 23 and so on
• Thus, a[1] is same as *(a +1) , *(1 + a) and 1[a]
• To summarize we can say that below 4 notations are the same

> • a[i]
• *(a + i)
• *(i + a)
• i[a]

## POINTERS AND 2-D ARRAYS

2-D arrays are arrays having 2 dimensions. It is also called a matrix
• Consider the declaration –
• int arr[4][2] = {
{100, 101},
{200, 201},
{300, 301},
{400,401}
};
• Here [4] represents the number of rows and [2] represents the number of columns of the 2-D array

The above arrangement highlights the fact a 2-D array is nothing but a collection of 1-D arrays placed after
one another
• In the above example we have 4 1-d arrays and each array consist of 2 elements. Thus the row subscript
represents the numbers of arrays and column subscript represents the number of element per array.

```c
/* Program 11*/
#include<stdio.h>
int main() {
int arr[4][2] = {
{100, 101},
{200, 201},
{300, 301},
{400,401}
};
int a,b;
for (a=0; a<=3; a++) {
printf (“
\n”);
for (b=0; b<=1; b++)
printf (“%d
\t”, arr[a][b]);
}
return 0;
}
```

```c
Output:
100 101
200 201
300 301
400 401
```

As we have discussed, a 2-D array is nothing
but a collection of 1-D arrays placed after one
another
• In the above example we have 4 1-d arrays and each array consist of 2 elements. Thus the row subscript represents the numbers of arrays and column subscript represents the number of element per array.
• Thus arr[4][2] can be interpreted as setting up 4 arrays of 2 elements each.
• Important concept here to note is arr[0] will give address of the 0th 1-D array , arr[1] will give the address of the 1st 1-D array, arr[2] will give the address of the 2nd 1-D array and so on. Refer to the program alongside for the explanation

```c
/* Program 12*/
#include<stdio.h>
int main()
{
int arr[4][2] = {
{100, 101},
{200, 201},
{300, 301},
{400,401}
};
int a;
for (a=0; a<=3; a++)
printf (“Address of the %d 1-D Array is %u \n”,a,arr[a]);
return 0;
}
Output:
Address of the 0 1-D Array is 2456
Address of the 1 1-D Array is 2464
Address of the 2 1-D Array is 2472
Address of the 3 1-D Array is 2480
```

## Array of Pointers and Returning Array
from a Function

### ARRAY OF POINTERS

An array of pointers is nothing but a collection of addresses
• The addresses present in it can be addresses of isolated variables or addresses of array elements or any other addresses

```c
/* Program 15*/
#include<stdio.h>
int main()
{
int *arr[4]; // Array of integer pointers
int i =1, j =3, k = 5, l = 7, a;
arr[0] = &I; arr[1] = &j; arr[2] = &k; arr[3] = &l;
for (a=0; a <= 3; a++)
printf(“%d\n”, *(arr[a]);
return 0;
}

OUTPUT:
1
3
5
7
```

### POINTERS TO AN ARRAY

- Here row is a pointer to an array of 2 integers. The round bracket is required to make understand C compiler that it is a pointer pointing to an array
- In the outer for loop each time we store the
address of a new 1-D array. In the 1s iteration
row will contain the address of the 0th 1-D
array. This address is then assigned to integer
pointer colpoint.

```c
// Program 13
#includestdio.h>
int main(){
int arr[4][2] = {
{100, 101}
{200,201},
{300, 301},
{400,401}}
int (*row)[2];//This is pointer of array of 2 integers
int a,b,*colpoint;
for (a=O; a<=3; a++)
{
	row &arr[a];
	colpoint = (int *)row ;// using typecast to assign pointer address
	printf("\n");
	for (b-0; b<=1; b++)
		printf("%d \t", *(colpoint + b));
}
return 0;
}
```

- In the outer for loop each time we store the address of a new 1-D array. In the 1st iteration row will contain the address of the 0th 1-D array. This address is then assigned to integer pointer colpoint

### PASSING 2D ARRAY TO A FUNCTION

In the show() function we have collected the base address of the 2-D array being passed to it in s, where s is pointer to an carray of 2
integers
The declaration of s looks like int s[ ][2]; which
is same as saying int (*s)[2]

```c
//*Program 14*
#include<stdio.h>
void show (int s[ 12], int, int )
int main(){
	
	int arr[4][2]= {{100, 101}, {200, 201}, {300, 301}, {400,401}};
	show(arr, 4,2);
	return 0;
}
void show(int s[][2], int row, int col)
int i, j;
for ( i =  0 i < row ; i+){
for ( j = 0; j < col ; j+)
	printf("%d \t",s[i][j]);
printf("\n");
}
printf("\n");

}
```

```c
OUTPUT:
100 101
200 201
300 301
400 401
```

### RETURNING ARRAY FROM A FUNCTION

• The most common way of returning 2-D array to a function is by returning the base address of the array (say an integer 2D array) as a pointer to an
integer
• In the example, fun() returns the base address as pointer to an integer
• The first pass of the inner for loop is evaluated as *(c+0*4+0) → *(c+0) and hence value printed is 1
• The value of b is incremented in the next iteration and the value is *(c+0*4+1) →*(c+1) and hence value printed is 3 and so on

```c
/* Program 16*/
#include<stdio.h>
int main()
{
int a,b;
int * fun(); // function prototype
int *c ;
c = fun();
for (a = 0 ; a < 3 ; a++)
{
for (b = 0 ; b<4; b++)
printf(“%d”, *(c + a*4 + b));
printf (“\n”);
}
return 0;
}
int *fun()
{
static int c[3][4] = { 1,3,5,7,
2,4,6,8,
9, 11, 13,15,
10,12,14,16}
return (int *) c;
}
```

```c
Output
1
3
5
7
2
4
6
8
9
11
13
15
10
12
14
16
```
