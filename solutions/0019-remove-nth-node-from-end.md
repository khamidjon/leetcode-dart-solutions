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
  ListNode? removeNthFromEnd(ListNode? head, int n) {
      ListNode dummy = ListNode(0, head);
      ListNode left = dummy;
      ListNode? right = head; 

      while(n > 0 && right != null){
          right = right.next;
          n -= 1;
      }

      while(right != null){
          left = left.next!;
          right = right.next;
      }

      final next = left.next;
      left.next = next!.next;

      return dummy.next;
  }
}
```
