
```
Given a sorted array nums, 
remove the duplicates in-place such that duplicates appeared 
at most twice and return the new length.

Do not allocate extra space for another array, 
you must do this by modifying the input array
in-place with O(1) extra memory.
```

![image](https://raw.githubusercontent.com/Octopus-10-8/Data-structures-and-algorithms/master/img/zy01.png)

---

```
Clarification:

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by reference, which means modification to the input array will be known to the caller as well.

Internally you can think of this:

// nums is passed in by reference. (i.e., without making a copy)
int len = removeDuplicates(nums);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```



```
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums == null) return -1;
        if (nums.length <= 2) return nums.length;

        int newIndex = 1;
        for (int i = 2; i < nums.length; i++) {
            if (nums[i] != nums[newIndex] || nums[i] != nums[newIndex - 1]) {
                newIndex++;
                nums[newIndex] = nums[i];
            }
        }

        return newIndex + 1;
    }
}
```
遍历数组时 i 从2开始，newIndex 初始化为1便于分析。时间复杂度 O(n)O(n), 空间复杂度 O(1)O(1).如果是三个重复，同理只需要添加 ||语句即可调整i的开始和index的初始值。

---

---
##### LeetCode热门解析：

```
public int removeDuplicates(int[] nums) {
    int i = 0;
    for (int n : nums)
        if (i < 2 || n > nums[i-2])
            nums[i++] = n;
    return i;
}
```

