# GFG_16
---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Strings
  - Sorting  
---

# 🚀 _Day 3. Anagram_ 🧠
The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/anagram-1587115620)

## 💡 **Problem Description:**

You are given two strings `s1` and `s2`, both consisting of lowercase alphabets. Your task is to check whether the two strings are anagrams of each other. Two strings are anagrams if they contain the same characters, but the order of characters may differ.

## 🔍 **Example Walkthrough:**

**Input:**  
`s1 = "geeks", s2 = "kseeg"`  
**Output:**  
`true`

**Explanation:**  
Both strings contain the same characters with the same frequency, so they are anagrams.

**Input:**  
`s1 = "allergy", s2 = "allergic"`  
**Output:**  
`false`

**Explanation:**  
The characters in both strings are not the same, so they are not anagrams.

**Input:**  
`s1 = "g", s2 = "g"`  
**Output:**  
`true`

**Explanation:**  
Both strings contain the same character, so they are anagrams.

### Constraints:
- $`1 ≤ s1.size(), s2.size() ≤ 10^5`$

## 🎯 **My Approach:**

1. **Character Counting**:  
   - Since anagrams contain the same characters with the same frequency, we can compare the frequency of characters in both strings.  
   - To do this efficiently, we use an array of size 26 (for the 26 lowercase letters) to count the frequency of characters in both strings.  
   - The idea is to increment the count for characters in `s1` and decrement the count for characters in `s2`. If the counts match after processing both strings, the strings are anagrams.

2. **Steps:**  
   - Check if both strings have the same length. If not, they cannot be anagrams.  
   - Iterate through the strings and update the frequency count for each character.  
   - After processing both strings, check if all the counts are zero. If they are, return `true`; otherwise, return `false`.

## 🕒 **Time and Auxiliary Space Complexity** 

- **Expected Time Complexity:** O(n), where `n` is the length of the strings. We traverse both strings once, performing constant-time operations for each character.
- **Expected Auxiliary Space Complexity:** O(1), as we only use a constant amount of additional space for the frequency count array (size 26).

## 📝 **Solution Code**`
## Code (Python)

```python
class Solution:
    def areAnagrams(self, s1, s2):
        if len(s1) != len(s2):
            return False

        counts = [0] * 26
        for i in range(len(s1)):
            counts[ord(s1[i]) - ord('a')] += 1
            counts[ord(s2[i]) - ord('a')] -= 1

        for count in counts:
            if count != 0:
                return False

        return True
```
