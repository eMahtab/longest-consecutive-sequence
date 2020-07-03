# Longest Consecutive Sequence
# https://leetcode.com/problems/longest-consecutive-sequence

# Implementation :

```java
class Solution {
    public int longestConsecutive(int[] nums) {
        if (nums == null || nums.length == 0) 
            return 0;

        Arrays.sort(nums);

        int longestStreak = 1;
        int currentStreak = 1;

        for (int i = 0; i < nums.length - 1; i++) {
            if (nums[i] != nums[i+1]) {
                if (nums[i] + 1 == nums[i+1]) {
                    currentStreak += 1;
                }
                else {
                    longestStreak = Math.max(longestStreak, currentStreak);
                    currentStreak = 1;
                }
            }
        }

        return Math.max(longestStreak, currentStreak);
    }
}
```
