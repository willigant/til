# Quickly clone an array

* Using `slice` we can quickly clone an array. This is useful
if you're running a pop of shift which mutates the original array

```
var arr =  [0,1,2,3,4,5];
var copied = arr.slice(0);

// mutating origial doesn't affect copied
arr.pop();
console.log(arr);
console.log(copied);
```
