# Counting Sort

Counting sort is an algorithm for sorting a collection of objects according to keys that are small integers; that is, it is an integer sorting algorithm. It operates by counting the number of objects that have each distinct key value, and using arithmetic on those counts to determine the positions of each key value in the output sequence.

```javascript
// Counting sort with max value parameter
const countingSort = (array, max) => {
  const counts = new Array(max + 1)
  counts.fill(0)
  array.forEach(value => counts[value]++)

  const result = []
  let resultIndex = 0

  counts.forEach((count, index) => {
    for (let i = 0; i < count; i++) {
      result[resultIndex] = index
      resultIndex++
    }
  })

  return result
}

// Counting sort with both Min and Max value as parameters
function countingSort(arr, min, max) {
  let i
  let z = 0
  const count = []

  for (i = min; i <= max; i++) {
    count[i] = 0
  }

  for (i = 0; i < arr.length; i++) {
    count[arr[i]]++
  }

  for (i = min; i <= max; i++) {
    while (count[i]-- > 0) {
      arr[z++] = i
    }
  }
  return arr
}
```

## Complexity

* Worst-case performance: `O(n+k)`, where k is the range of the non-negative key values.
* Worst-case space: `O(n+k)`

## References

* https://en.wikipedia.org/wiki/Counting_sort
