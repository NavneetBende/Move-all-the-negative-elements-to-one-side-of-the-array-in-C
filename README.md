Move all negative elements to one side of the array  in C
Here, in this page we will discuss the program to move all negative elements to one side of the array in C . We use the concept of two pointers to do so . We are giving with the size of the array along with array elements .We have to print array as desired.

Example :  Input : n= 5
                                arr[5] = { 9, 1, -2, 4, -8}

                    Output : -2 -8 9 1 4

Move all negative elements to one side of the array in C
Algorithm :
Take the size of the array from the user and store it in variable say n.
Now, declare a vector of size n and take the n elements of the vector say arr from the user.
Take two variables like left and right which hold the 0 and n-1 indexes.
Just need to check that :

Check If the left and right pointer elements are negative then simply increment the left pointer.
Otherwise, if the left element is positive and the right element is negative then simply swap the elements, and simultaneously increment and decrement the left and right pointers.
Else if the left element is positive and the right element is also positive then simply decrement the right pointer.
Repeat the above 3 steps until the left pointer ≤ right pointer.
Move all negative elements to one side
Code in C
#include <stdio.h>

void shiftall(int arr[], int left, int right)
{

  while (left<=right)
  {
     if (arr[left] < 0 && arr[right] < 0)
      left+=1;

     else if (arr[left]>0 && arr[right]<0)
     {
        int temp=arr[left];
        arr[left]=arr[right];
        arr[right]=temp;
        left+=1;
        right-=1;
     }

     else if (arr[left]>0 && arr[right] >0)
        right-=1;

     else{
        left += 1;
        right -= 1;
     }
   }
}

void display(int arr[], int right){

    for (int i=0;i<=right;++i){
      printf("%d ",arr[i]);
    }
    printf("\n");
}

int main()
{
   int n;
   scanf("%d", &n);

   int arr[n];

   for(int i=0; i<n; i++)
     scanf("%d", &arr[i]);

   // Function Call
   shiftall(arr,0,n-1);
   display(arr,n-1);
   return 0;
}
Output :
5
8 9 10 -2 7

-2 8 9 10 7
