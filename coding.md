Easy Level (15 Questions)
1. Find the largest element in a list
```python
python

def find_largest(arr):
    return max(arr)

# Test
print(find_largest([1, 5, 3, 9, 2]))  # 9
```

2. Find the second largest element
```python
python
def second_largest(arr):
    unique = list(set(arr))
    unique.sort()
    return unique[-2] if len(unique) >= 2 else None

print(second_largest([10, 20, 4, 45, 99]))  # 45
```





3. Check if list is sorted
python
```python
def is_sorted(arr):
    return all(arr[i] <= arr[i+1] for i in range(len(arr)-1))

print(is_sorted([1, 2, 3, 4]))  # True
print(is_sorted([1, 3, 2, 4]))  # False
```




4. Reverse a list
python
```python
def reverse_list(arr):
    return arr[::-1]

print(reverse_list([1, 2, 3, 4]))  # [4, 3, 2, 1]
```




5. Find sum of all elements
python
```python
def list_sum(arr):
    return sum(arr)

print(list_sum([1, 2, 3, 4, 5]))  # 15
```





```python
6. Find average of list

```python
def list_average(arr):
    return sum(arr) / len(arr) if arr else 0

print(list_average([10, 20, 30, 40]))  # 25.0



7. **Remove duplicates from list**
python
def remove_duplicates(arr):
    return list(set(arr))

print(remove_duplicates([1, 2, 2, 3, 4, 4, 5]))  # [1, 2, 3, 4, 5]
8. Count frequency of element
python
def count_frequency(arr, target):
    return arr.count(target)

print(count_frequency([1, 2, 3, 2, 4, 2, 5], 2))  # 3





9. Find common elements between two lists
python
def common_elements(list1, list2):
    return list(set(list1) & set(list2))

print(common_elements([1, 2, 3, 4], [3, 4, 5, 6]))  # [3, 4]
10. Merge two sorted lists
python
def merge_sorted_lists(list1, list2):
    return sorted(list1 + list2)

print(merge_sorted_lists([1, 3, 5], [2, 4, 6]))  # [1, 2, 3, 4, 5, 6]




11. Find all even numbers
python
def find_even_numbers(arr):
    return [x for x in arr if x % 2 == 0]

print(find_even_numbers([1, 2, 3, 4, 5, 6]))  # [2, 4, 6]




12. Square all elements
python
def square_elements(arr):
    return [x**2 for x in arr]

print(square_elements([1, 2, 3, 4]))  # [1, 4, 9, 16]




13. Find minimum element
python
def find_min(arr):
    return min(arr)

print(find_min([5, 2, 8, 1, 9]))  # 1





14. Check if element exists
python
def element_exists(arr, target):
    return target in arr

print(element_exists([1, 2, 3, 4, 5], 3))  # True




15. Find length of list
python
def list_length(arr):
    return len(arr)

print(list_length([1, 2, 3, 4, 5]))  # 5





Medium Level (20 Questions)
16. Rotate list by k positions
python
def rotate_list(arr, k):
    k = k % len(arr)
    return arr[-k:] + arr[:-k]

print(rotate_list([1, 2, 3, 4, 5], 2))  # [4, 5, 1, 2, 3]





17. Find all pairs with given sum
python
def find_pairs(arr, target_sum):
    pairs = []
    seen = set()
    for num in arr:
        complement = target_sum - num
        if complement in seen:
            pairs.append((complement, num))
        seen.add(num)
    return pairs

print(find_pairs([1, 5, 7, -1, 5], 6))  # [(1, 5), (7, -1), (1, 5)]





18. Move all zeros to end
python
def move_zeros(arr):
    non_zeros = [x for x in arr if x != 0]
    zeros = [0] * (len(arr) - len(non_zeros))
    return non_zeros + zeros

print(move_zeros([0, 1, 0, 3, 12]))  # [1, 3, 12, 0, 0]






19. Find missing number in sequence
python
def find_missing_number(arr):
    n = len(arr) + 1
    total_sum = n * (n + 1) // 2
    return total_sum - sum(arr)

print(find_missing_number([1, 2, 4, 5, 6]))  # 3






20. Find duplicates in list
python
def find_duplicates(arr):
    seen = set()
    duplicates = set()
    for num in arr:
        if num in seen:
            duplicates.add(num)
        seen.add(num)
    return list(duplicates)

print(find_duplicates([1, 2, 3, 2, 4, 5, 4]))  # [2, 4]




21. Find intersection of two lists
python
def intersection(list1, list2):
    return [x for x in list1 if x in list2]

print(intersection([1, 2, 3, 4], [3, 4, 5, 6]))  # [3, 4]



22. Find maximum subarray sum (Kadane's Algorithm)
python
def max_subarray_sum(arr):
    max_sum = current_sum = arr[0]
    for num in arr[1:]:
        current_sum = max(num, current_sum + num)
        max_sum = max(max_sum, current_sum)
    return max_sum

print(max_subarray_sum([-2, 1, -3, 4, -1, 2, 1, -5, 4]))  # 6






23. Find leaders in array
python
def find_leaders(arr):
    leaders = []
    max_right = float('-inf')
    for i in range(len(arr)-1, -1, -1):
        if arr[i] >= max_right:
            leaders.append(arr[i])
            max_right = arr[i]
    return leaders[::-1]

print(find_leaders([16, 17, 4, 3, 5, 2]))  # [17, 5, 2]




24. Find first non-repeating element
python
def first_non_repeating(arr):
    from collections import Counter
    count = Counter(arr)
    for num in arr:
        if count[num] == 1:
            return num
    return None

print(first_non_repeating([1, 2, 3, 2, 1, 4]))  # 3





25. Find majority element
python
def majority_element(arr):
    from collections import Counter
    count = Counter(arr)
    return max(count.items(), key=lambda x: x[1])[0]

print(majority_element([3, 3, 4, 2, 4, 4, 2, 4, 4]))  # 4




26. Find kth largest element
python
def kth_largest(arr, k):
    return sorted(arr)[-k]

print(kth_largest([3, 2, 1, 5, 6, 4], 2))  # 5



27. Find kth smallest element
python
def kth_smallest(arr, k):
    return sorted(arr)[k-1]




print(kth_smallest([3, 2, 1, 5, 6, 4], 3))  # 3
28. Find all permutations of list
python
def permutations(arr):
    from itertools import permutations
    return list(permutations(arr))


    

print(permutations([1, 2, 3]))  # [(1, 2, 3), (1, 3, 2), (2, 1, 3), ...]
29. Find longest consecutive sequence
python
def longest_consecutive_sequence(arr):
    num_set = set(arr)
    longest = 0
    for num in num_set:
        if num - 1 not in num_set:
            current_num = num
            current_streak = 1
            while current_num + 1 in num_set:
                current_num += 1
                current_streak += 1
            longest = max(longest, current_streak)
    return longest

print(longest_consecutive_sequence([100, 4, 200, 1, 3, 2]))  # 4




30. Find product except self
python
def product_except_self(arr):
    n = len(arr)
    result = [1] * n
    left_product = right_product = 1
    
    for i in range(n):
        result[i] = left_product
        left_product *= arr[i]
    
    for i in range(n-1, -1, -1):
        result[i] *= right_product
        right_product *= arr[i]
    
    return result

print(product_except_self([1, 2, 3, 4]))  # [24, 12, 8, 6]





31. Find all subsets
python
def subsets(arr):
    result = [[]]
    for num in arr:
        result += [curr + [num] for curr in result]
    return result

print(subsets([1, 2, 3]))  # [[], [1], [2], [1,2], [3], [1,3], [2,3], [1,2,3]]






32. Find maximum product subarray
python
def max_product_subarray(arr):
    if not arr:
        return 0
    max_prod = min_prod = result = arr[0]
    for i in range(1, len(arr)):
        if arr[i] < 0:
            max_prod, min_prod = min_prod, max_prod
        max_prod = max(arr[i], max_prod * arr[i])
        min_prod = min(arr[i], min_prod * arr[i])
        result = max(result, max_prod)
    return result

print(max_product_subarray([2, 3, -2, 4]))  # 6




33. Find container with most water
python
def max_area(height):
    left, right = 0, len(height) - 1
    max_area = 0
    while left < right:
        current_area = min(height[left], height[right]) * (right - left)
        max_area = max(max_area, current_area)
        if height[left] < height[right]:
            left += 1
        else:
            right -= 1
    return max_area

print(max_area([1, 8, 6, 2, 5, 4, 8, 3, 7]))  # 49




34. Find three sum
python
def three_sum(arr, target):
    arr.sort()
    result = []
    for i in range(len(arr)-2):
        if i > 0 and arr[i] == arr[i-1]:
            continue
        left, right = i+1, len(arr)-1
        while left < right:
            current_sum = arr[i] + arr[left] + arr[right]
            if current_sum == target:
                result.append([arr[i], arr[left], arr[right]])
                while left < right and arr[left] == arr[left+1]:
                    left += 1
                while left < right and arr[right] == arr[right-1]:
                    right -= 1
                left += 1
                right -= 1
            elif current_sum < target:
                left += 1
            else:
                right -= 1
    return result

print(three_sum([-1, 0, 1, 2, -1, -4], 0))  # [[-1, -1, 2], [-1, 0, 1]]





35. Find next permutation
python
def next_permutation(arr):
    i = len(arr) - 2
    while i >= 0 and arr[i] >= arr[i+1]:
        i -= 1
    if i >= 0:
        j = len(arr) - 1
        while arr[j] <= arr[i]:
            j -= 1
        arr[i], arr[j] = arr[j], arr[i]
    arr[i+1:] = reversed(arr[i+1:])
    return arr

print(next_permutation([1, 2, 3]))  # [1, 3, 2]
Hard Level (15 Questions)





36. Find median of two sorted arrays
python
def find_median_sorted_arrays(nums1, nums2):
    merged = sorted(nums1 + nums2)
    n = len(merged)
    if n % 2 == 0:
        return (merged[n//2 - 1] + merged[n//2]) / 2
    else:
        return merged[n//2]

print(find_median_sorted_arrays([1, 3], [2]))  # 2.0




37. Find trapping rain water
python
def trap_rain_water(height):
    if not height:
        return 0
    left, right = 0, len(height) - 1
    left_max = right_max = water = 0
    while left < right:
        if height[left] < height[right]:
            if height[left] >= left_max:
                left_max = height[left]
            else:
                water += left_max - height[left]
            left += 1
        else:
            if height[right] >= right_max:
                right_max = height[right]
            else:
                water += right_max - height[right]
            right -= 1
    return water

print(trap_rain_water([0,1,0,2,1,0,1,3,2,1,2,1]))  # 6





38. Find minimum in rotated sorted array
python
def find_min_rotated(arr):
    left, right = 0, len(arr) - 1
    while left < right:
        mid = (left + right) // 2
        if arr[mid] > arr[right]:
            left = mid + 1
        else:
            right = mid
    return arr[left]

print(find_min_rotated([4, 5, 6, 7, 0, 1, 2]))  # 0






39. Search in rotated sorted array
python
def search_rotated(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        if arr[left] <= arr[mid]:
            if arr[left] <= target < arr[mid]:
                right = mid - 1
            else:
                left = mid + 1
        else:
            if arr[mid] < target <= arr[right]:
                left = mid + 1
            else:
                right = mid - 1
    return -1

print(search_rotated([4, 5, 6, 7, 0, 1, 2], 0))  # 4







40. Find first and last position in sorted array
python
def search_range(arr, target):
    def find_first():
        left, right = 0, len(arr) - 1
        while left <= right:
            mid = (left + right) // 2
            if arr[mid] >= target:
                right = mid - 1
            else:
                left = mid + 1
        return left if left < len(arr) and arr[left] == target else -1
    
    def find_last():
        left, right = 0, len(arr) - 1
        while left <= right:
            mid = (left + right) // 2
            if arr[mid] <= target:
                left = mid + 1
            else:
                right = mid - 1
        return right if right >= 0 and arr[right] == target else -1
    
    return [find_first(), find_last()]

print(search_range([5, 7, 7, 8, 8, 10], 8))  # [3, 4]






41. Find k closest elements
python
def find_closest_elements(arr, k, x):
    left, right = 0, len(arr) - k
    while left < right:
        mid = (left + right) // 2
        if x - arr[mid] > arr[mid + k] - x:
            left = mid + 1
        else:
            right = mid
    return arr[left:left + k]

print(find_closest_elements([1, 2, 3, 4, 5], 4, 3))  # [1, 2, 3, 4]





42. Find peak element
python
def find_peak_element(arr):
    left, right = 0, len(arr) - 1
    while left < right:
        mid = (left + right) // 2
        if arr[mid] > arr[mid + 1]:
            right = mid
        else:
            left = mid + 1
    return left

print(find_peak_element([1, 2, 3, 1]))  # 2





43. Find duplicate number
python
def find_duplicate(arr):
    slow = fast = arr[0]
    while True:
        slow = arr[slow]
        fast = arr[arr[fast]]
        if slow == fast:
            break
    slow = arr[0]
    while slow != fast:
        slow = arr[slow]
        fast = arr[fast]
    return slow

print(find_duplicate([1, 3, 4, 2, 2]))  # 2









44. Find missing and repeating numbers
python
def find_missing_repeating(arr):
    n = len(arr)
    total_sum = n * (n + 1) // 2
    total_sq_sum = n * (n + 1) * (2 * n + 1) // 6
    
    arr_sum = sum(arr)
    arr_sq_sum = sum(x*x for x in arr)
    
    diff_sum = total_sum - arr_sum  # missing - repeating
    diff_sq_sum = total_sq_sum - arr_sq_sum  # missing² - repeating²
    
    sum_xy = diff_sq_sum // diff_sum  # missing + repeating
    
    missing = (diff_sum + sum_xy) // 2
    repeating = sum_xy - missing
    
    return [repeating, missing]

print(find_missing_repeating([1, 3, 3]))  # [3, 2]









45. Find inversion count
python
def inversion_count(arr):
    def merge_count(arr, temp, left, right):
        if left >= right:
            return 0
        mid = (left + right) // 2
        count = 0
        count += merge_count(arr, temp, left, mid)
        count += merge_count(arr, temp, mid + 1, right)
        count += merge(arr, temp, left, mid, right)
        return count
    
    def merge(arr, temp, left, mid, right):
        i, j, k = left, mid + 1, left
        count = 0
        while i <= mid and j <= right:
            if arr[i] <= arr[j]:
                temp[k] = arr[i]
                i += 1
            else:
                temp[k] = arr[j]
                count += (mid - i + 1)
                j += 1
            k += 1
        while i <= mid:
            temp[k] = arr[i]
            i += 1
            k += 1
        while j <= right:
            temp[k] = arr[j]
            j += 1
            k += 1
        for i in range(left, right + 1):
            arr[i] = temp[i]
        return count
    
    temp = [0] * len(arr)
    return merge_count(arr, temp, 0, len(arr) - 1)

print(inversion_count([8, 4, 2, 1]))  # 6





46. Find maximum sum circular subarray
python
def max_circular_sum(arr):
    def kadane(arr):
        max_sum = current_sum = arr[0]
        for num in arr[1:]:
            current_sum = max(num, current_sum + num)
            max_sum = max(max_sum, current_sum)
        return max_sum
    
    max_kadane = kadane(arr)
    total_sum = sum(arr)
    max_wrap = total_sum + kadane([-x for x in arr])
    return max(max_kadane, max_wrap) if max_wrap != 0 else max_kadane

print(max_circular_sum([5, -3, 5]))  # 10



47. Find longest increasing subsequence
python
def length_of_lis(arr):
    if not arr:
        return 0
    dp = [1] * len(arr)
    for i in range(1, len(arr)):
        for j in range(i):
            if arr[i] > arr[j]:
                dp[i] = max(dp[i], dp[j] + 1)
    return max(dp)

print(length_of_lis([10, 9, 2, 5, 3, 7, 101, 18]))  # 4

48. Find word break possibilities
python
def word_break(s, word_dict):
    word_set = set(word_dict)
    dp = [False] * (len(s) + 1)
    dp[0] = True
    for i in range(1, len(s) + 1):
        for j in range(i):
            if dp[j] and s[j:i] in word_set:
                dp[i] = True
                break
    return dp[len(s)]

print(word_break("leetcode", ["leet", "code"]))  # True



49. Find maximum product of word lengths
python
def max_product_words(words):
    n = len(words)
    masks = [0] * n
    lens = [0] * n
    for i, word in enumerate(words):
        for char in word:
            masks[i] |= 1 << (ord(char) - ord('a'))
        lens[i] = len(word)
    
    max_prod = 0
    for i in range(n):
        for j in range(i + 1, n):
            if not (masks[i] & masks[j]):
                max_prod = max(max_prod, lens[i] * lens[j])
    return max_prod

print(max_product_words(["abcw", "baz", "foo", "bar", "xtfn", "abcdef"]))  # 16





50. Find number of islands in grid
python
def num_islands(grid):
    if not grid:
        return 0
    
    def dfs(i, j):
        if i < 0 or i >= len(grid) or j < 0 or j >= len(grid[0]) or grid[i][j] != '1':
            return
        grid[i][j] = '0'
        dfs(i + 1, j)
        dfs(i - 1, j)
        dfs(i, j + 1)
        dfs(i, j - 1)
    
    count = 0
    for i in range(len(grid)):
        for j in range(len(grid[0])):
            if grid[i][j] == '1':
                count += 1
                dfs(i, j)
    return count

grid = [
    ['1','1','0','0','0'],
    ['1','1','0','0','0'],
    ['0','0','1','0','0'],
    ['0','0','0','1','1']
]
print(num_islands(grid))  # 3




These questions cover a wide range of difficulties and concepts including:

Basic list operations

Sorting and searching algorithms

Two-pointer techniques

Dynamic programming

Binary search applications

Graph algorithms on grid representations

Mathematical problems using lists

Each solution is optimized and includes test cases to verify correctness