# Sorting 

There are 6 main types of **Comparison-Based Sorting**:
- Bubble Sort
- Insertion Sort
- Selection Sort
- Quick Sort
- Merge Sort
- Heap Sort
  
This Markdown contains: 
- A sufficient explanation as to the **mechanisms** of each sorting technique
- The meanings and how **time and space complexities** were derived in each instance
- When and where to use each sorting technique
- Relevant codes 

## Bubble Sort

Bubble Sort, as far as I'm aware, is the slowest sorting algorithm. It's the most intuitive and simplest algorithm out of the 6 algorithms.
It's why I started with this. Had I started with Heap Sort, I would probably not want to continue because of how much more complex that is in 
comparison.

Idea - Compare adjacent indices. If the current index is greater than the next index, swap them so that the current index goes closer to the end position of the array.

Pointer iterations - 

0 1 

1 2 

2 3 

3 4


0 1 

1 2

2 3


0 1

1 2


0 1

```
import random

class SortingTechniques:
    def testingTheClass(arr):
        return arr

    # BUBBLE SORT FUNCTION BELOW
    def bubbleSort(arr):
        curr = len(arr) - 1
        while curr >= 1:
            for i in range(0, curr):
                if arr[i + 1] < arr[i]:
                    arr[i], arr[i + 1] = arr[i + 1], arr[i]
            curr -= 1
        return arr
      
        
        
# An array defined for sorting 
arr = [random.randint(1, 100) for _ in range(5)]

print(SortingTechniques.testingTheClass(arr))
print(SortingTechniques.bubbleSort(arr))
```

Note: We can optimize this by stopping the loop if there were no swaps on the first iteration. But that is self-explanatory and doesn't need to be explained.

Time Complexities :-

Best - O(n)
Average - O(n^2)
Worst - O(n^2)

- The Best Case can be obtained when **no swaps are made** on the first iteration (implying that the array is already sorted).
- The Average Case is n <= x <= n^2, and since the array cannot be preempted because there is no intelligence to determine whether its sorted at the instance, the complexity is O(n^2).
- The Worst Case is O(n^2) (requiring the maximum number of swaps) as both of the pointers must traverse from 0 to curr for every iteration.

Now, this may be difficult to understand intuitively, so this is how I picture it. The algorithm works to put the **highest element at the top** after every iteration. We can say for sure that, the last position in the array will be filled with the highest element in the array after all of the traversals. 

Therefore, if we traversed 'n - 1' times, we could sort 'n - 1' elements from beginning to end. Pretty simple when it's layed out like that.

## Insertion Sort

This was pretty confusing to me at first, but I think this is best understood by performing manual dry runs. I enjoy this one though, it's very interesting. It doesn't immediately make sense why it works, but after reading this, it'll make sense.

Idea - Assume the array is sorted and set a pointer to the second element. Traverse through the sorted array and find the position in which we can insert the current index element into the sorted array to keep it sorted. 

Pointer iterations - 

1 0 


2 1 

2 0 


3 2 

3 1 

3 0


4 3 

4 2

4 1 

4 0

```
import random

class SortingTechniques:
    def testingTheClass(arr):
        return arr

    
    def bubbleSort(arr):
        curr = len(arr) - 1
        while curr >= 1:
            for i in range(0, curr):
                if arr[i + 1] < arr[i]:
                    arr[i], arr[i + 1] = arr[i + 1], arr[i]
            curr -= 1
        return arr
        
    def insertionSort(arr):
        for i in range(1, 5):
            j = i
            while j > 0 and arr[j - 1] > arr[j]:
                arr[j - 1], arr[j] = arr[j], arr[j - 1]
                j = j - 1
            print(arr)
        
# An array defined for sorting 
arr = [random.randint(1, 100) for _ in range(5)]

print(SortingTechniques.testingTheClass(arr))
print(SortingTechniques.insertionSort(arr))
```

This is a slight improvement on Bubble Sort, and the time complexities are the same. 

Best Case is when the array is sorted, and the Worst Case is when the array is sorted in reverse.
Now how can we understand the worst case? What does 'reverse order' imply?
'Reverse order' implies that the highest element is at the beginning. In insertion sort, the smallest elements are inserted before the pivot element
in order to keep the array (until pivot) sorted. Picture a queue waiting to get a coffee. Insertion sort is like sending all of the people in the 
front of the queue to the back. Kind of is a hassle.


This is how I picture it. This is kind of building a pyramid of legos, where the legos are of different sizes. But we know that, the bottom lego has 
to be the longest and the top lego has to be the shortest. We are trying to ensure that the **bottom section BEFORE the pivot** is always organized
in order. Pretty easy when it's layed out organized at all times, and you have to insert one lego to keep the order.

## Selection Sort

Okay, this one. It's very self explanatory as to how it sorts. It just drags the minimum to the beginning of the array. It's very simple to write the algorithm, and as for the pointer iterations, its just from start to end. 

Pointer iterations - 

0 1 -> n
1 2 -> n 
n - 1 n -> n



























