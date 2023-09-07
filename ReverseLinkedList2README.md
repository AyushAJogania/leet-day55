# leet-day55

# Problem Description

Given the head of a singly linked list and two integers, `left` and `right`, where `left` <= `right`, you need to reverse the nodes of the list from position `left` to position `right` and return the reversed list.

## Example

Input: `head = [1,2,3,4,5], left = 2, right = 4`

Output: `[1,4,3,2,5]`

## Constraints

- The number of nodes in the list is `n`.
- `1 <= n <= 500`
- `-500 <= Node.val <= 500`
- `1 <= left <= right <= n`

## Approach

To solve this problem, we can use a simple one-pass approach with pointers. Here are the steps:

1. Initialize pointers `prev`, `curr`, and `next` to `nullptr`. Also, create a dummy node and set its next pointer to the head of the list. This dummy node will help in handling the case when `left` is 1.

2. Move the `prev` pointer `left - 1` times to reach the node just before the left position. At the end of this step, `prev` will point to the node before the sublist to be reversed.

3. Initialize `curr` and `next` pointers as `prev->next` and `prev->next->next`, respectively. These pointers will be used to reverse the sublist.

4. Reverse the sublist from `left` to `right` in a similar way as you would reverse a singly linked list. Use a loop to reverse the pointers.

5. After reversing the sublist, connect the `prev` and `next` pointers to the appropriate nodes in the reversed sublist.

6. Return the `dummy.next` as the new head of the list.

## Pseudocode

Here's a pseudocode representation of the approach:

```plaintext
1. Initialize pointers prev, curr, and next as nullptr.
2. Create a dummy node and set its next pointer to the head of the list.
3. Move prev to the node just before the left position (prev will be at position left - 1).
4. Initialize curr and next as prev->next and prev->next->next.
5. Reverse the sublist from left to right:
   - While curr is not at the right position:
     - Update curr->next to next->next.
     - Update next->next to prev->next.
     - Update prev->next to next.
     - Update next to curr->next.
6. Return dummy.next as the new head of the list.
```

## Complexity Analysis

The time complexity of this approach is O(n), where n is the number of nodes in the linked list, as we traverse the list once. The space complexity is O(1), as we use a constant amount of extra space for pointers.

# Conclusion

The "Reverse Linked List II" problem is solved efficiently using a one-pass approach with pointers. By following the provided approach and pseudocode, you can reverse a sublist of a singly linked list with ease.
