# [206. Reverse Linked List (Easy)](https://leetcode.com/problems/reverse-linked-list/)

## Recursive Approach

**Analysis:**
- Time complexity: `O(n)`
- Space complexity: `O(1)`

**Submission Detail:**

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* curr = head;
        ListNode* prev = NULL;
        ListNode* next = NULL;
        while (curr != NULL) {
            next = curr->next;
            curr->next = prev;
            prev = curr;
            curr= next;
        }
        return prev;
    }
};
```

```
Runtime: 14 ms, faster than 16.05% of C++ online submissions for Reverse Linked List.
Memory Usage: 8.3 MB, less than 80.24% of C++ online submissions for Reverse Linked List.
```
