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
comparison



```
import random

class SortingTechniques:
    def testingTheClass(arr):
        return arr
    
    def <span style="color: yellow;">bubbleSort</span>(arr):
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











