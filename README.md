

# Data Structures & Algorithm
 All data structures &amp; algorithm  code with description.
 ## Topic :
 
<details><summary> Linear Search </summary>

### Linear Search in C
 >Linear search is also called as sequential search algorithm. It is the simplest searching algorithm. In Linear search, we simply traverse the list completely and match each element of the list with the item whose location is to be found. If the match is found, then the location of the item is returned; otherwise, the algorithm returns NULL.
 ```c
 #include<stdio.h>
int main()
{
    int i, number, position=-1, item[20] = {3,6,1,9,5,2,4,8};
    printf("Enter Search Number:  ");
    scanf("%d",&number);

    for(i=0;i<=7;i++ )
    {
        if(item[i] == number)
        {
            position=i+1;
            break;
        }
    }

    if(position == -1)
    {
        printf("\n Searching number is not found.\n\n");
    }else
    {
        printf("\nSearching number is %d that is found.\nIt position is %d \n\n ",number,position-1);
    }

    return 0;
}
 ```
#### Output:
![linear-search](https://user-images.githubusercontent.com/57310861/164992828-b0bdb4a1-eb44-4f6c-97e0-66c9ff4fbda6.PNG)
</details>
 
 <details><summary> Binary search </summary>

### Binary search in C
 >Binary search is a fast search algorithm with run-time complexity of Ο(log n). This search algorithm works on the principle of divide and conquer. For this algorithm to work properly, the data collection should be in the sorted form.
 ```c
  #include<Stdio.h>
int main()
{
    int list[10] = {2,4,6,9,12,15,16,20};
    int start=0,end=7,key = 6;

    do
    {
        int mid =(int)((start+end)/2);
        if(list[mid] == key)
        {
            printf("searching value: %d  | Location: %d \n",list[mid],mid+1);
            break;
        }
        else if(list[mid]>key)
        {
            end=mid-1;
        }
        else
        {
            start=mid+1;
        }
    }
    while(start<=end);

    if(start>end)
    {
        printf("searching value is not found./n");
    }
    return 0;
}

 ```
#### Output:
![Binary-search](https://github.com/mahmud-hosen/Data-Structures-Algorithm/blob/main/File/image/Binary-search.PNG?raw=true)
  
</details>
  
  <details><summary> Insertion Sort </summary>

### Insertion Sort in C
 >Insertion sort is a simple sorting algorithm that builds the final sorted array one item at a time. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort.
 ```c
   #include<Stdio.h>
int main()
{
    int i,j,temp,list[10] = {9,7,4,3,1};

    for(int i=0;i<=4;i++)
    {
        j=i;
        while(j>0 && list[j] < list[j-1])
        {
            temp = list[j];
            list[j] = list[j-1];
            list[j-1] = temp;
            j--;
        }
    }

    printf("\n Ascending order:");
    for(int i=0;i<=4;i++)
    {
        printf(" %d ",list[i]);
    }
    printf("\n");
    return 0;
}
 ```
#### Output:
![Insertion Sort](https://github.com/mahmud-hosen/Data-Structures-Algorithm/blob/main/File/image/Binary-search.PNG?raw=true)
  
</details>

 <details><summary> Bubble Sort </summary>

### Bubble Sort in C
 >Bubble sort is a simple sorting algorithm. This sorting algorithm is comparison-based algorithm in which each pair of adjacent elements is compared and the elements are swapped if they are not in order.
 ```c
  #include<Stdio.h>
int main()
{
    int i,j,temp, list[10] ={10,6,4,3,2,1};
    for(i=0;i<=5;i++)
    {
        for(j=i+1;j<=5;j++)
        {
            if(list[i]>list[j])
            {
                temp=list[j];
                list[j]=list[i];
                list[i]=temp;

            }
        }
    }
    printf("\n Assending Order:");
    for(i=0;i<=5;i++)
    {
        printf(" %d ",list[i]);
    }
    return 0;
}
 ```
#### Output:
![Bubble Sort](https://github.com/mahmud-hosen/Data-Structures-Algorithm/blob/main/File/image/Binary-search.PNG?raw=true)
  
</details>

  <details><summary> Quick Sort </summary>

### Quick Sort in C
 >The quicksort algorithm is a sorting algorithm that works by selecting a pivot point, and thereafter partitioning the number set, or array, around the pivot point.
 ```c
   #include<Stdio.h>
int main()
{
    int number[10] = {15,13,8,5,3};
    quicksort(number,0,4);

    printf(" \n Assending Order: ");
    for(int i=0;i<=4;i++)
    {
        printf(" %d ",number[i]);
    }
    printf("\n");

    return 0;
}
void quicksort(int number[10],int left,int right)
{
    int pivot,i,j,temp;
    if(left<right)
    {
        pivot=left, i=left, j=right;
        while(i<j)
        {
            while(number[pivot] >= number[i] && i<right)
            {
                i++;
            }
            while(number[pivot] < number[j])
             {
                 j--;
             }
            if(i<j){
				temp=number[i];
				number[i]=number[j];
				number[j]=temp;
			 }
        }

          temp=number[pivot];
		  number[pivot]=number[j];
		  number[j]=temp;

		  quicksort(number,left,j-1);
		  quicksort(number,j+1,right);
    }
}

 ```
#### Output:
![Quick Sort](https://github.com/mahmud-hosen/Data-Structures-Algorithm/blob/main/File/image/Binary-search.PNG?raw=true)
  
</details>
	  
	  
	  
 <details><summary> Stack  </summary>

### Stack in C
 >A stack (sometimes called a “push-down stack”) is an ordered collection of items where the addition of new items and the removal of existing items always takes place at the same end.
 ```c
#include<Stdio.h>
int MAXSIZE = 8;
int stack[8];
int top = -1;

int isfull()
{
    if(top == MAXSIZE)
    {
        return 1;
    }else
    {
        return 0;
    }
}

int isempty()
{
    if(top == -1)
    {
        return 1;
    }else
    {
        return 0;
    }
}
int push(int data)
{
    if(!isfull())
    {
        top=top+1;
        stack[top]=data;
    }else
    {
        printf("Stack  is Full");
    }
}
// POP Function
int pop()
{
    int data;
    if(!isempty())
    {
        data = stack[top];
        top=top-1;
        return data;
    }else
    {
        printf("Stack is empty");
    }
}
int main()
{
    push(3);
    push(6);
    push(1);
    push(10);
    push(5);
    push(7);
    push(15);
    push(4);
    push(17);
     pop();
    push(13);

    printf("\nStack: ");
    for(int i=0;i<=top;i++)
    {
        printf(" %d ",stack[i]);
    }
    printf("\n");
    return 0;
}
	 
 ```
#### Output:
![Stack](https://github.com/mahmud-hosen/Data-Structures-Algorithm/blob/main/File/image/Binary-search.PNG?raw=true)
  
</details>
