💡 Sample Explanation: Merge Sort
Step-by-Step Breakdown
1️⃣ Defining the Function
python
Copy
Edit
def merge_sort(arr):
def → Defines a function in Python
merge_sort → Function name for Merge Sort algorithm
arr → Input array to be sorted
2️⃣ Base Case for Recursion
python
Copy
Edit
if len(arr) > 1:
if → Checks a condition
len(arr) → Finds the number of elements in arr
> 1 → If array has one element, it’s already sorted
3️⃣ Divide the Array into Two Halves
python
Copy
Edit
mid = len(arr) // 2
left_half = arr[:mid]
right_half = arr[mid:]
mid → Finds the middle index
left_half → Stores the left portion of the array
right_half → Stores the right portion
4️⃣ Recursively Sort the Two Halves
python
Copy
Edit
merge_sort(left_half)
merge_sort(right_half)
Calls merge_sort on left and right halves until single elements remain
5️⃣ Merge the Sorted Halves
python
Copy
Edit
i = j = k = 0
while i < len(left_half) and j < len(right_half):
    if left_half[i] < right_half[j]:
        arr[k] = left_half[i]
        i += 1
    else:
        arr[k] = right_half[j]
        j += 1
    k += 1
Merges two sorted halves by comparing elements
Uses i, j, k pointers to track progress
6️⃣ Handle Remaining Elements
python
Copy
Edit
while i < len(left_half):
    arr[k] = left_half[i]
    i += 1
    k += 1

while j < len(right_half):
    arr[k] = right_half[j]
    j += 1
    k += 1
Ensures all elements are merged correctly
✅ Example Walkthrough
📌 Input: [38, 27, 43, 3]
📌 Steps:

Split into [38, 27] and [43, 3]
Sort [38, 27] into [27, 38]
Sort [43, 3] into [3, 43]
Merge [27, 38] and [3, 43] → [3, 27, 38, 43]
