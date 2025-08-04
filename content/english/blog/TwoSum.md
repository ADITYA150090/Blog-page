---
title: "1. Two Sum - Brute Force to Optimal"
meta_title: "Two Sum Problem in DSA with Brute Force and Optimal Solutions"
description: "Understand the Two Sum problem from Leetcode with brute force, better, and optimal solutions explained step-by-step."
date: 2025-05-02T05:00:00Z
image: "/images/twosum.png"
categories: ["DSA", "Leetcode"]
author: "Aditya Dhawle"
tags: ["HashTable", "Array"]
draft: false
---

### 🧠 Problem Statement

> Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to the target.  
> 
> You may assume that each input would have **exactly one solution**, and **you may not use the same element twice**.  
> 
> You can return the answer in **any order**.

---

## 🧪 Example

Input: nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explanation: nums[0] + nums[1] = 2 + 7 = 9


---

### ❌ Brute Force Approach

#### 🔍 Idea:
Try every possible pair and check if their sum is equal to the target.

#### 🧾 Steps:
- Loop over each element `i`.
- For every `i`, loop over the remaining elements `j > i`.
- If `nums[i] + nums[j] == target`, return the indices.

#### 🧮 Time Complexity:
- **O(n²)** — because of the nested loops

#### ✅ Code (Java):

```java
public int[] twoSum(int[] nums, int target) {
    for (int i = 0; i < nums.length; i++) {
        for (int j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] == target) {
                return new int[]{i, j};
            }
        }
    }
    return new int[]{-1, -1}; // fallback
}
```

### ⚡ Better Approach (Using HashMap)
#### 🔍 Idea:
Instead of checking every pair, we use a HashMap to store visited elements and their indices.

While iterating, check if target - nums[i] exists in the map.

#### 🧾 Steps:
Create an empty HashMap<Integer, Integer> to store value → index.

For each element nums[i], calculate complement = target - nums[i].

If complement exists in map → we found the pair.

Otherwise, store nums[i] → i in the map.

#### ⏱ Time Complexity:
O(n) — Single pass through array

#### ✅ Code (Java):
```java
public int[] twoSum(int[] nums, int target) {
    HashMap<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
        int complement = target - nums[i];
        if (map.containsKey(complement)) {
            return new int[]{map.get(complement), i};
        }
        map.put(nums[i], i);
    }
    return new int[]{-1, -1}; // fallback
}


```

#### 🚀 Optimal Solution: Explanation in Plain English
Let’s say the array is [2, 7, 11, 15] and the target is 9.

Start at index 0 → value is 2 → we want 7 (because 9-2=7).

Is 7 in the map? No. So store 2:0 in the map.

Move to index 1 → value is 7 → 9-7 = 2.

Is 2 in the map? Yes! We found our answer → [0, 1].

#### ✍️ Conclusion
Brute force is good to start understanding the problem.

HashMap-based approach is the go-to optimal solution in interviews.

Always look for ways to store useful info during iteration.