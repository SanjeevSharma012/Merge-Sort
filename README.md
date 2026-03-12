# Merge Sort in Java

This project implements the **Merge Sort algorithm** in Java using recursion and the divide-and-conquer technique.

## 📌 Description

Merge Sort is a sorting algorithm that divides the array into smaller subarrays, sorts them recursively, and then merges the sorted subarrays to produce the final sorted array.

It is one of the most efficient and stable sorting algorithms.

## ⚙️ Algorithm Steps

1. Divide the array into two halves.
2. Recursively sort both halves.
3. Merge the two sorted halves into a single sorted array.

## 💻 Java Implementation

```java
class Solution {

    void mergeSort(int arr[], int l, int r) {
        if (l >= r) return;

        int mid = l + (r - l) / 2;

        mergeSort(arr, l, mid);
        mergeSort(arr, mid + 1, r);

        merge(arr, l, mid, r);
    }

    void merge(int[] arr, int l, int mid, int r) {
        int[] c = new int[r - l + 1];

        int k = 0;
        int i = l;
        int j = mid + 1;

        while (i <= mid && j <= r) {
            if (arr[i] <= arr[j]) c[k++] = arr[i++];
            else c[k++] = arr[j++];
        }

        while (i <= mid) {
            c[k++] = arr[i++];
        }

        while (j <= r) {
            c[k++] = arr[j++];
        }

        for (i = l, j = 0; j < c.length; i++, j++) {
            arr[i] = c[j];
        }
    }
}
⏱ Time Complexity
Case	Complexity
Best Case	O(n log n)
Average Case	O(n log n)
Worst Case	O(n log n)
📦 Space Complexity
O(n)

Merge Sort requires additional space for the temporary array used during merging.

🚀 Features

Efficient for large datasets

Stable sorting algorithm

Uses divide-and-conquer strategy

👨‍💻 Author

Sanjeev Sharma.
