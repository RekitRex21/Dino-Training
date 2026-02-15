# Coding Benchmark Prompts for rex-dino-qwen3

## Setup Instructions
1. In Terminal (keep htop for monitoring)
2. Run each prompt with verbose mode:
```bash
ollama run rex-dino-qwen3 --verbose "YOUR PROMPT HERE"
```
3. Copy generated code → paste into Python file → run to verify

## 5 Coding Tasks

### Task 1: Easy – String Manipulation
**Prompt:**
Write a Python function called `has_close_elements` that takes a list of numbers (floats) and a threshold (float). It should return True if any two numbers in the list are closer than the threshold, False otherwise. Use O(n^2) is fine for small lists.

Example:
- has_close_elements([1.0, 2.8, 3.0, 4.9, 5.0], 0.3) -> True (2.8 and 3.0 are 0.2 apart)
- has_close_elements([1.0, 2.0, 3.0], 0.5) -> False

---

### Task 2: Medium – List Processing + Sorting
**Prompt:**
Write a Python function `sort_numbers` that takes a string of space-separated numbers (0-9 as words like "zero", "one", ..., "nine") and returns the same string but sorted from smallest to largest.

Example:
- sort_numbers("three one five") -> "one three five"
- sort_numbers("nine eight seven six five four three two one zero") -> "zero one two three four five six seven eight nine"
- sort_numbers("") -> ""

---

### Task 3: Medium – Prime Check + List Comprehension
**Prompt:**
Write a function `filter_by_prefix` that takes a list of strings and a prefix string. Return a new list with only the strings that start with the prefix.

Example:
- filter_by_prefix([], "a") -> []
- filter_by_prefix(["abc", "bcd", "cde", "array"], "a") -> ["abc", "array"]
- filter_by_prefix(["hello", "world"], "x") -> []

---

### Task 4: Harder – Algorithm + Edge Cases
**Prompt:**
Write a function `fibonacci_sum_even` that returns the sum of all even Fibonacci numbers up to (but not including) n. Use efficient iteration (no recursion). Handle n <= 0 gracefully (return 0).

Examples:
- fibonacci_sum_even(10) -> 10 (Fib: 0,1,1,2,3,5,8 → evens: 0+2+8=10)
- fibonacci_sum_even(100) -> 44 (0+2+8+34)
- fibonacci_sum_even(2) -> 0

---

### Task 5: Advanced – Data Structures + Logic
**Prompt:**
Write a function `find_median_sorted_arrays` that takes two sorted lists of integers nums1 and nums2, and returns the median of the two sorted arrays merged. Do it in O(log (m+n)) time if possible (binary search), but O(m+n) is acceptable.

Examples:
- find_median_sorted_arrays([1,3], [2]) -> 2.0
- find_median_sorted_arrays([1,2], [3,4]) -> 2.5
- find_median_sorted_arrays([], [1]) -> 1.0
- find_median_sorted_arrays([2], []) -> 2.0

---

## Scoring
- Pass: Code runs correctly on examples + handles edges
- Bonus: Good style (PEP8-ish, comments, efficiency)
- Run multiple times to test consistency
- Use `--temperature 0.2` for deterministic results
