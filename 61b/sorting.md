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

  Runtime wise, merge sort is always $$\Theta(N\log(N))$$ in both the worst and best case.                    

## Insertion Sort

* Designate i as a traveling item.
* Swap it backwards until the item is in the right place.

In the best case, we get a $$\Theta(N)$$ runtime — furthermore, this runtime is actually the same as the runtime for an almost sorted list. Unfortunately, in the case of the average case, we have $$\Theta(N^2)$$ .

{% hint style="info" %}
Any comparison based sort uses at least $$\Theta(N\log N) $$ comparisons.
{% endhint %}

## Counting Sort

In order to avoid the previous constraint, we can just sort without comparing.  If items in a list have some kind of key, and those keys have some kind of ordering to them, we can 

* Count the number of times each key occurs
* Iterate through list and place into new list, using cumulative count array to decide where everything goes.

## LSD Radix Sort

This is a counting sort that does not rely on an alphabet keys having a finite length. We just sort by each digit independently, in this case doing a counting sort by the least significant digit. When keys are of different lengths, just treat the empty spaces as less than all the other digits. 

