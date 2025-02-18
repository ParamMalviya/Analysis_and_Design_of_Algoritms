Line-by-Line Explanation:
1. Defining the Function
python
Copy
def merge_sort(arr):
def: This keyword is used to define a function in Python.

merge_sort: This is the name of the function. It will perform the merge sort algorithm.

arr: This is the input parameter, which is the array (or list) that we want to sort.

2. Base Case for Recursion
python
Copy
if len(arr) > 1:
if: This is a conditional statement. It checks whether a condition is true.

len(arr): This gives the length (number of elements) of the array arr.

> 1: We check if the array has more than one element. If it does, we proceed with sorting. If not, the array is already sorted (base case for recursion).

3. Divide the Array into Two Halves
python
Copy
mid = len(arr) // 2
left_half = arr[:mid]
right_half = arr[mid:]
mid: This calculates the middle index of the array.

len(arr) // 2: The // operator performs integer division. For example, if len(arr) is 5, then 5 // 2 gives 2.

left_half: This is the left half of the array, from the start (arr[0]) to the middle (arr[mid-1]).

right_half: This is the right half of the array, from the middle (arr[mid]) to the end (arr[-1]).

4. Recursively Sort the Two Halves
python
Copy
merge_sort(left_half)
merge_sort(right_half)
merge_sort(left_half): This recursively calls the merge_sort function on the left half of the array.

merge_sort(right_half): This recursively calls the merge_sort function on the right half of the array.

Recursion: This means the function calls itself. It keeps dividing the array into smaller halves until each subarray has only one element (base case).

5. Initialize Pointers for Merging
python
Copy
i = j = k = 0
i: This is a pointer for the left_half array.

j: This is a pointer for the right_half array.

k: This is a pointer for the original array arr.

All three pointers start at 0, meaning we start comparing and merging from the beginning of each array.

6. Merge the Two Sorted Halves
python
Copy
while i < len(left_half) and j < len(right_half):
    if left_half[i] < right_half[j]:
        arr[k] = left_half[i]
        i += 1
    else:
        arr[k] = right_half[j]
        j += 1
    k += 1
while: This is a loop that continues as long as the condition is true.

i < len(left_half) and j < len(right_half): This checks if both pointers (i and j) are within the bounds of their respective arrays.

if left_half[i] < right_half[j]: This compares the current element of the left_half with the current element of the right_half.

If the element in left_half is smaller, it is placed in the original array arr at position k.

Otherwise, the element in right_half is placed in arr.

i += 1 and j += 1: These increment the pointers after an element is placed in arr.

k += 1: This moves the pointer in the original array arr to the next position.

7. Handle Remaining Elements in Left Half
python
Copy
while i < len(left_half):
    arr[k] = left_half[i]
    i += 1
    k += 1
This loop checks if there are any remaining elements in the left_half that haven't been merged yet.

If so, they are added to the original array arr.

8. Handle Remaining Elements in Right Half
python
Copy
while j < len(right_half):
    arr[k] = right_half[j]
    j += 1
    k += 1
This loop checks if there are any remaining elements in the right_half that haven't been merged yet.

If so, they are added to the original array arr.

Example Walkthrough:
Let’s say the input array is [38, 27, 43, 3].

Divide:

The array is split into [38, 27] and [43, 3].

Recursively Sort:

[38, 27] is split into [38] and [27], then merged as [27, 38].

[43, 3] is split into [43] and [3], then merged as [3, 43].

Merge:

The two sorted halves [27, 38] and [3, 43] are merged into [3, 27, 38, 43].

Key Concepts:
Divide and Conquer: The array is divided into smaller subarrays, sorted, and then merged.

Recursion: The function calls itself to sort smaller subarrays.

Merging: Two sorted subarrays are combined into one sorted array.
