# Quick Sort

Quicksort is a divide and conquer algorithm. Quicksort first divides a large array into two smaller sub-arrays: the low elements and high elements. Quicksort can then recursively sort the sub-arrays. The steps are:

1. Pick an element, called a pivot, from the array
2. Partition: reorder the array so that all elements with values less than pivot come before the pivot, while all elements with values greater than the pivot come after it(equal values can go either way). After this partitioning, the pivot is in its final position. This is called partition operation.
3. Recursively apply the above the steps to the sub-array of elements with smaller values and separately to the sub-array of elements with greater values.

The base case of the recursion is arrays of size 0 or 1, which are in order by definition, so they never need to be sorted.

The pivot selection and partitioning steps can be done in several different ways; the choice of specific implementation schemes greatly affects the algorithm's performance.

```javascript
// Swap helper
function swap(arr, i, j) {
  const temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
}

function partition(arr, pivot, left, right) {
  const pivotValue = arr[pivot]
  let partitionIndex = left

  for (let i = left; i < right; i++) {
    if (arr[i] < pivotValue) {
      swap(arr, i, partitionIndex)
      partitionIndex++
    }
  }
  swap(arr, right, partitionIndex)
  return partitionIndex
}

function quickSort(arr, left, right) {
  if (left < right) {
    const pivot = right
    const partitionIndex = partition(arr, pivot, left, right)

    // Sort left and right
    quickSort(arr, left, partitionIndex - 1)
    quickSort(arr, partitionIndex + 1, right)
  }
  return arr
}

// Args are the indexed positions, 2 of them.
console.log(quickSort([11, 8, 14, 3, 6, 2, 7], 0, 6))

```

## Complexity

* Worst-case performance: `O(n^2)`
* Best-case performance: `O(n log n)`(simple partition) or `O(n)`(three-way partition and equal keys)
* Average-case performance: `O(n log n)`

## References

* https://en.wikipedia.org/wiki/Quicksort