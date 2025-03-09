# Can-Place-Flowers---LeetCode-605---Solution

# 🌸 Can Place Flowers - LeetCode Solution

## 📝 Problem Statement
You are given a flowerbed represented as an array, where:
- `0` means an empty plot.
- `1` means a flower is already planted.
- Flowers **cannot be planted in adjacent plots**.

You need to determine whether **n new flowers** can be planted **without violating the rules**.

---

## ✅ Example Inputs & Outputs
### Example 1:
```cpp
Input: flowerbed = [1,0,0,0,1], n = 1
Output: true
```

### Example 2:
```cpp
Input: flowerbed = [1,0,0,0,1], n = 2
Output: false
```


## 🚀 Optimized C++ Solution
```cpp
class Solution {
public:
    bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        int count = 0;
        int size = flowerbed.size();

        for (int i = 0; i < size; i++) {
            if (flowerbed[i] == 0) {  
                if ((i == 0 || flowerbed[i - 1] == 0) && (i == size - 1 || flowerbed[i + 1] == 0)) {
                    flowerbed[i] = 1;
                    count++;
                    if (count >= n) return true;
                    i++; // Skip next plot
                }
            }
        }

        return count >= n;
    }
};
```

---

## 📌 Complexity Analysis
- **Time Complexity**: `O(N)` (Iterates through the flowerbed once)
- **Space Complexity**: `O(1)` (Uses no extra space)

---

3. Test with different inputs.

---

## 🛠 Future Improvements
- Implement an alternative **greedy approach**.
- Optimize with **early exit conditions**.
- Explore **different data structures** for better efficiency.

---

## 🎯 Contribute
Feel free to **fork**, improve, or suggest optimizations! 🚀  
⭐ If this helped, please **star** the repo!

---
