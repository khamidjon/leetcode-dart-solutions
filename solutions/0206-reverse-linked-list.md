```
/**
 * Definition for singly-linked list.
 * class ListNode {
 *   int val;
 *   ListNode? next;
 *   ListNode([this.val = 0, this.next]);
 * }
 */
class Solution {
  ListNode? reverseList(ListNode? head) {
      if (head == null) {
          return null;
      }

      ListNode? prev = null;
      ListNode? curr = head;
      
      while (curr != null) {
          ListNode? nxt = curr.next;
          curr.next = prev;
          prev = curr;
          curr = nxt;
      }
      return prev;
  }
}
```
