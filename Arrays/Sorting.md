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

The Best Case can be obtained when **no swaps are made** on the first iteration (implying that the array is already sorted).
The Average Case is n <= x <= n^2, and since the array cannot be preempted because there is no intelligence to determine whether its sorted at the instance, the complexity is O(n^2).
The Worst Case is O(n^2) (requiring the maximum number of swaps) as both of the pointers must traverse from 0 to curr for every iteration.

Now, this may be difficult to understand intuitively, so this is how I picture it. The algorithm works to put the **highest element at the top** after every iteration. We can say for sure that, the last position in the array will be filled with the highest element in the array after all of the traversals. 

Therefore, if we traversed 'n - 1' times, we could sort 'n - 1' elements from beginning to end. Pretty simple when it's layed out like that.


















