# [234. Palindrome Linked List (Easy)](https://leetcode.com/problems/palindrome-linked-list/)

## Fast and Slow Pointer Approach

**Analysis:**
- Time complexity: `O(n)`
- Space complexity: `O(n)`

**Submission Detail:**

```cpp
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:

    def isPalindrome(self, head: ListNode) -> bool:
        slow, fast = head, head
        stack = []
        while (fast is not None) and (fast.next is not None):
            stack.append(slow.val)
            slow = slow.next
            fast = fast.next.next
        if fast is not None:
            slow = slow.next
        while slow is not None:
            if slow.val != stack.pop():
                return False
            slow = slow.next
        return True 
```

```
Runtime: 409 ms, faster than 18.94% of C++ online submissions for Palindrome Linked List.
Memory Usage: 120.8 MB, less than 41.54% of C++ online submissions for Palindrome Linked List.
```
