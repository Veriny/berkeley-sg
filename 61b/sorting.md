# Sorting

## Selection sort

Selection sort involves the following.

* Find the smallest item in the unsorted part of the array.
* Move it to the end of the sorted array.
* Repeat for the rest of the unsorted portion, until the unsorted portion no longer exists.

This is slow. We need $$\Theta(N^2)$$ time to run it.

## Heapsort

A naive implementation would involve inserting all the elements into a max heap, and then removing every element from the heap and adding it to an imput array. We can save space by doing the following.

* Bottom up heapify the the input array — sink nodes in reverse level order.
* Delete largest item from the heap, swapping this item with the last one in the heap array.

Runtime is linear for an array of all duplicates, but the worst case runtime is $$\Theta(NlogN)$$ and it uses constant space.

## Merge Sort

* Split items into 2 even pieces.
* Merge sort each half.
* Merge two sorted halves to form the final result.
  * Compare the items in the list, whichever one is lesser add it to the final array until there's no more left of the two merge sorted arrays.

## Insertion Sort

* Designate i as a traveling item.
* Swap it backwards until the item is in the right place.

