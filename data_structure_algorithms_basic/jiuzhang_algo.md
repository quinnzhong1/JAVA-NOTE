# 九章算法模板

## Search - Recursion - Backtracking

### 排列组合模板

* 例题
  * lintcode17: Given a set with distinct integers, return all possible subsets (in any order).
  * ![](./algorithms_pic/lintcode17-solution.png)
  * lintcode18: Given a collection of integers that might contain duplicate numbers, return all possible subsets.
  * ![](./algorithms_pic/lintcode18-solution.png)

* 适用范围
  * 似乎所有搜索问题，会有细微改动
  * 什么时候输出
  * 哪些情况需要跳过
  * ![](./algorithms_pic/backtracking-model.png)

## binary search
* 所有比较全部统一`<`或者`<=`
```java
class Solution {
    // First Search
    public int binarySearch(int[] nums, int target) {
        if (nums == null) || (nums.length == 0) {
            return -1;
        }

        int left = 0;
        int right = nums.length - 1;

        while (left + 1 < right) { // 为了使得退出循环的时候left和right是挨着的(或者相等，如果一开始left和right就是相等的），并且mid始终没有取到left或者right（mid如果等于left或者right可能出现死循环）
            int mid = left + (right - left) / 2;  //防止溢出
            if (nums[mid] == target) {
                right = mid; //往左，找第一个position
                //找最后一个position
                //left = mid;
            } else if (nums[mid] < target) {
                left = mid;
            } else {
                right = mid;
            }
        } //核心：一直二分到只剩两个数

        if (nums[left] == target) {
            return left;
        }
        if (nums[right] == target) {
            return right;
        }

        return -1;
    }
}
```
```java
class Solution {
    //LastSearch
    public int binarySearch(int[] nums, int target) {
        if (nums == null) || (nums.length == 0) {
            return -1;
        }

        int left = 0;
        int right = nums.length - 1;

        while (left + 1 < right) { // 为了使得退出循环的时候left和right是挨着的(或者相等，如果一开始left和right就是相等的），并且mid始终没有取到left或者right（mid如果等于left或者right可能出现死循环）
            int mid = left + (right - left) / 2;  //防止溢出
            if (nums[mid] == target) {
                left = mid; //往左，找第一个position
                //找最后一个position
                //left = mid;
            } else if (nums[mid] < target) {
                left = mid;
            } else {
                right = mid;
            }
        } //核心：一直二分到只剩两个数

        //这个前后顺序不要搞错
        if (nums[right] == target) {
            return right;
        }
        if (nums[left] == target) {
            return left;
        }

        return -1;
    }
}
```

* 使用场景：
  * 需要优化O(n)的暴力算法（除了logn，还有1，n，根号n可以用于优化n）
  * Sorted array or Ratated sorted array
* logn算法：
  * 二分法
  * 倍增法
* lintcode
![](./algorithms_pic//lintcode_premium_1.png)