# Merge Sort

Merge sort is an efficient, general-purpose, comparison-based sorting algorithm. Most implementations produce a stable sort, which means that the order of equal elements is the same in the input and output. Like Quicksort, Merge sort is also a divide and conquer algorithm.

> In computer science, divide and conquer is an algorithm design paradigm based on multi-branched recursion. A divide-and-conquer algorithm works by recursively breaking down a problem into two or more sub-problems of the same or related type, until these become simple enough to be solved directly. The solutions to the sub-problems are then combined to give a solution to the original problem.

Conceptually, a merger sort works as follows:

1. Divide the unsorted list into `n` sublists, each containing one element. A list of one element is inherently sorted.
2. Repeatedly merge sorted sublists (called "runs") to product longer runs until there is only one run remaining. This is the sorted list.

The pattern of merges forms a tree structure; in the common case that binary(two-way) merges are used, it forms a binary tree.

```javascript
const merge = (left, right) => {
  const result = []
  const leftLen = left.length
  const rightLen = right.length
  let l = 0
  let r = 0
  while (l < leftLen && r < rightLen) {
    if (left[l] < right[r]) {
      result.push(left[l])
      l++
    } else {
      result.push(right[r])
      r++
    }
  }
  return result.concat(left.slice(l)).concat(right.slice(r))
}

const mergeSort = arr => {
  const len = arr.length
  if (len < 2) {
    return arr
  }
  const mid = Math.floor(len / 2)
  const left = arr.slice(0, mid)
  const right = arr.slice(mid)
  return merge(mergeSort(left), mergeSort(right))
}
```

## Complexity
* Worst-case performance `O(n log n)`
* Best-case performance `O(n log n)` typical, `O(n)`natural variant
* Average performance `O(n log n)`

## Reference
* https://en.wikipedia.org/wiki/Merge_sort