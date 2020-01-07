# Quick Sort


```javascript
// Swap helper
const swap = (arr, i, j) => {
  const temp = arr[i]
  arr[i] = arr[j]
  arr[j] = temp
}

const partition = (arr, left, right) => {
  let q = left
  let i
  for (i = left; i < right; i++) {
    if (arr[i] < arr[right]) {
      swap(arr, i, q)
      q++
    }
  }
  swap(arr, i, q)
  return q
}

const quickSort = (arr, left, right) => {
  if (left < right) {
    const pivot = partition(arr, left, right)
    quickSort(arr, left, pivot - 1)
    quickSort(arr, pivot + 1, right)
    return arr
  }
}

console.log(quickSort([11, 8, 14, 3, 6, 2, 7], 0, 6))

```

## Complexity
## References