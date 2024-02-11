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
  ListNode? sortList(ListNode? head) {
      if(head?.next == null){
          return head;
      }

      ListNode? left = head!;
      ListNode? right = getMid(head);
      ListNode temp = right.next!;
      right.next = null;
      right = temp;

      left = sortList(left);
      right = sortList(right);
      return merge(left, right);
  }

  ListNode getMid(ListNode node){
      ListNode slow = node;
      ListNode? fast = node.next;

      while(fast?.next != null){
          slow = slow.next!;
          fast = fast!.next!.next;
      }
      return slow;
  }

  ListNode? merge(ListNode? left, ListNode? right) {
      ListNode dummy = ListNode();
      ListNode? tail = dummy;

      while(left != null && right != null){
          if(left.val < right.val){
              tail!.next = left;
              left = left.next;
          } else {
              tail!.next = right;
              right = right.next;
          }
          tail = tail?.next;
      }
      if(left != null){
          tail!.next = left;
      }

      if(right != null){
          tail!.next = right;
      }
      return dummy.next;
  }
}
```
