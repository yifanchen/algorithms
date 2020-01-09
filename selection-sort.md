# Selection Sort

Selection sort is a compareison sort and is quite simple. Go through an array, find the index of the lowest element and swap it with the first element in the array. The first elemnet then becomes the lowest element in the array. Now, go through the rest of the array until all the elements are sorted.

```javascript
function s(a) {
  const l = a.length

  for (let i = 0; i < l; i++) {
    let minIndex = i
    for (let j = i + 1; j < l; j++) {
      if (a[j] < a[i]) {
        minIndex = j
      }
    }
    const temp = a[i]
    a[i] = a[minIndex]
    a[minIndex] = temp
  }
  return a
}

console.log(s([3, 2, 1]))
```

## Complexity

* Worst-case performance: `O(n^2)` comparisons, `O(n)` swaps
* Best-case performance: `O(n^2)` comparisons, `O(n)` swaps
* Average-case performance: `O(n^2)` comparisons, `O(n)` swaps

## References
* https://en.wikipedia.org/wiki/Selection_sort