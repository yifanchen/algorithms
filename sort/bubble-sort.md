# Bubble Sort

Bubble sort, sometimes referred to as shinking sort, is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order.

<img src="./imgs/Bubble-sort-example-300px.gif">

```javascript
const s = a => {
  const l = a.length
  for (let i = 0; i < l; i++) {
    for (let j = 0; j < l; j++) {
      // When first index is greater than second index
      if (a[j] > a[j + 1]) {
        // Store temp value in second index and swap them
        const temp = a[j + 1]
        a[j + 1] = a[j]
        a[j] = temp
      }
    }
  }
  return a
}

console.log(s([3, 2, 1])) // 1, 2, 3
```

## Complexity

* Worst-case performance: `O(n^2)`
* Best-case performance: `O(n)`
* Average-case performance: `O(n^2)`

## References
* https://en.wikipedia.org/wiki/Bubble_sort