<h2>💡 Sample Explanation: Merge Sort</h2>

<h3>1️⃣ Defining the Function</h3>
<pre><code>
def merge_sort(arr):
</code></pre>
<ul>
    <li><strong>def</strong> → Defines a function in Python</li>
    <li><strong>merge_sort</strong> → Function name for Merge Sort algorithm</li>
    <li><strong>arr</strong> → Input array to be sorted</li>
</ul>

<h3>2️⃣ Base Case for Recursion</h3>
<pre><code>
if len(arr) > 1:
</code></pre>
<ul>
    <li><strong>if</strong> → Checks a condition</li>
    <li><strong>len(arr)</strong> → Finds the number of elements in arr</li>
    <li><strong>> 1</strong> → If the array has one element, it’s already sorted</li>
</ul>

<h3>3️⃣ Divide the Array into Two Halves</h3>
<pre><code>
mid = len(arr) // 2
left_half = arr[:mid]
right_half = arr[mid:]
</code></pre>
<ul>
    <li><strong>mid</strong> → Finds the middle index</li>
    <li><strong>left_half</strong> → Stores the left portion of the array</li>
    <li><strong>right_half</strong> → Stores the right portion</li>
</ul>

<h3>4️⃣ Recursively Sort the Two Halves</h3>
<pre><code>
merge_sort(left_half)
merge_sort(right_half)
</code></pre>
<ul>
    <li>Calls <strong>merge_sort</strong> on left and right halves until single elements remain</li>
</ul>

<h3>5️⃣ Merge the Sorted Halves</h3>
<pre><code>
i = j = k = 0
while i < len(left_half) and j < len(right_half):
    if left_half[i] < right_half[j]:
        arr[k] = left_half[i]
        i += 1
    else:
        arr[k] = right_half[j]
        j += 1
    k += 1
</code></pre>
<ul>
    <li>Merges two sorted halves by comparing elements</li>
    <li>Uses <strong>i, j, k</strong> pointers to track progress</li>
</ul>

<h3>6️⃣ Handle Remaining Elements</h3>
<pre><code>
while i < len(left_half):
    arr[k] = left_half[i]
    i += 1
    k += 1

while j < len(right_half):
    arr[k] = right_half[j]
    j += 1
    k += 1
</code></pre>
<ul>
    <li>Ensures all elements are merged correctly</li>
</ul>

<h3>✅ Example Walkthrough</h3>
<ul>
    <li>📌 <strong>Input:</strong> <code>[38, 27, 43, 3]</code></li>
    <li>📌 <strong>Steps:</strong></li>
    <ul>
        <li>Split into <code>[38, 27]</code> and <code>[43, 3]</code></li>
        <li>Sort <code>[38, 27]</code> into <code>[27, 38]</code></li>
        <li>Sort <code>[43, 3]</code> into <code>[3, 43]</code></li>
        <li>Merge <code>[27, 38]</code> and <code>[3, 43]</code> → <code>[3, 27, 38, 43]</code></li>
    </ul>
</ul>
