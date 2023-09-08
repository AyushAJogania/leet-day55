# leet-day55

# Problem Statement

Given the head of a singly linked list, reverse the list, and return the reversed list.

## Example

**Input**: `[1, 2, 3, 4, 5]`
**Output**: `[5, 4, 3, 2, 1]`

**Input**: `[1, 2]`
**Output**: `[2, 1]`

**Input**: `[]`
**Output**: `[]`

# Solution Approach - Iterative

## Algorithm

1. Initialize three pointers: `prev`, `curr`, and `nextNode`. `prev` is initially set to `nullptr`, `curr` to `head`.

2. While `curr` is not `nullptr`:
    a. Store the next node in `nextNode`.
    b. Reverse the `next` pointer of `curr` to point to `prev`.
    c. Move `prev` and `curr` one step forward.
    d. Update `curr` to `nextNode`.

3. Return `prev` as the new head of the reversed list.


## Time Complexity

The time complexity of this solution is O(n), where n is the number of nodes in the linked list, as it processes each node once.

## Space Complexity

The space complexity is O(1), as it uses a constant amount of extra space for the pointers.

# Solution Approach - Recursive

## Algorithm

1. Handle the base case: If the `head` is `nullptr` or `head->next` is `nullptr`, return `head` as is.

2. Recursively reverse the sublist starting from the second node (i.e., `head->next`) and store the result in `reversedList`.

3. Reverse the `next` pointers of the first node (`head`) to point to `nullptr` and the second node to point to the first node.

4. Return `reversedList` as the new head of the reversed list.

## Pseudocode

```cpp
ListNode* reverseList(ListNode* head) {
    if (head == nullptr || head->next == nullptr) {
        return head;
    }

    ListNode* reversedList = reverseList(head->next);

    head->next->next = head;
    head->next = nullptr;

    return reversedList;
}
```

## Time Complexity

The time complexity of the recursive solution is O(n), as it processes each node once.

## Space Complexity

The space complexity is O(n) due to the recursive call stack, as there could be n recursive calls on the stack in the worst case.
