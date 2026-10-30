# Insert-Greatest-Common-Divisors-in-Linked-List
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def insertGreatestCommonDivisors(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if head is None:
            return head
        temp=head
        r=[]
        while temp:
            r.append(temp.val)
            temp=temp.next
        n=len(r)
        r1=[]
        for i in range(n-1):
            r1.append(r[i])
            r1.append(math.gcd(r[i],r[i+1]))
        r1.append(r[n-1])
        d=ListNode(0)
        temp=d
        for i in r1:
            temp.next=ListNode(i)
            temp=temp.next
        return d.next
