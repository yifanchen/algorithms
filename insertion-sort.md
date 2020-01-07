# Insertion Sort

Insertion sort is simple sorting algorithm that builds the final sorted array(or list) one item at a time. It is much less efficient on large lists.

![Insertion Sort](imgs/Insertion-sort-example-300px.gif)

Description

The best way I have seen to describe Insertion Sort is that imagine you are playing cards. Now your job is to sort the cards, so you pull the first card out and hold it in your hands as a key, you then compare it with the second card. If it is samller, you put it in postion A or otherwise you put it in position B.

Advantages:
* Simple implementation
* Efficient for small data sets, much like other quadratic sorting algorithms
* More efficient in practice than most other simple quadratic(i.e., O(n^2)) algorithms such as selection sort or bubble sort
* Adapitive, i.e., efficient for data sets that are already substantially sorted
* Stable, i.e., does not change the realtive order of elements with equal keys
* In-place, i.e., only requires a constant amount O(1) of additional memory space
* Online, i.e., can sort a list as it receives it

When people manually sort cards in bridge hand, most use a method that is similar to insertion sort.

```javascript
const s = a => {
  const l = a.length

  for (let i = 1; i < l; i++) {
    const key = a[i]
    let j = i

    while (j > 0 && a[j - 1] > key) {
      a[j] = a[j - 1]
      j--
    }
    a[j] = keyj
  }
  return a
}
```

## Complexity

* Worst-case performance: O(n^2)
* Best-case performance: O(n)
* Average-case performance: O(n^2)

## References

* https://en.wikipedia.org/wiki/Insertion_sort