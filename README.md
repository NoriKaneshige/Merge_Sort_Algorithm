# Merge_Sort_Algorithm


![merge_sort_animation](merge_sort_animation.gif)

![merge_sort_1](https://github.com/NoriKaneshige/Merge_Sort_Algorithm/blob/master/merge_sort_1.png)
![merge_sort_2](https://github.com/NoriKaneshige/Merge_Sort_Algorithm/blob/master/merge_sort_2.png)
![merge_sort_3](https://github.com/NoriKaneshige/Merge_Sort_Algorithm/blob/master/merge_sort_3.png)
![merge_sort_0](https://github.com/NoriKaneshige/Merge_Sort_Algorithm/blob/master/merge_sort_0.png)

> ## Merges two already sorted arrays: :wink:

``` js
function merge(arr1, arr2){
    let results = [];
    let i = 0;
    let j = 0;
    while(i < arr1.length && j < arr2.length){
        if(arr2[j] > arr1[i]){
            results.push(arr1[i]);
            i++;
        } else {
            results.push(arr2[j])
            j++;
        }
    }
    while(i < arr1.length) {
        results.push(arr1[i])
        i++;
    }
    while(j < arr2.length) {
        results.push(arr2[j])
        j++;
    }
    return results;
}

console.log(merge([100,200], [1,2,3,5,6]))
// [
//   1,   2,   3, 5,
//   6, 100, 200
// ]
```            

> ## Recrusive Merge Sort: :laughing:

``` js
function mergeSort(arr){
    if(arr.length <= 1) return arr;
    let mid = Math.floor(arr.length/2);
    let left = mergeSort(arr.slice(0,mid));
    let right = mergeSort(arr.slice(mid));
    return merge(left, right);
}

mergeSort([10,24,76,73]) // [10,24,73,76]
```
