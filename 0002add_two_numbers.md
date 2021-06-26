```
// stupid way
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
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        
        // cout << l1 << endl;
        // cout << l1->val;
 
        int inc = 0,a=0,b=0,c=0;
        ListNode *l3=new ListNode(-1); 
 
        // ListNode* p1=l1;
        // ListNode* p2=l2;
        ListNode* p3=l3;
        
        while(l1!=NULL or l2!=NULL or inc!=0  ){  
            a=l1!=NULL?l1->val:0;
            b=l2!=NULL?l2->val:0;
            
            c=(a+b+inc)%10;
            inc=(a+b+inc)/10;
            
            if(l1) l1=l1->next;
            if(l2) l2=l2->next;
            
            if (p3->val == -1) {
                p3->val = c;
            }
            else {
                p3->next  = new ListNode(c) ;
                p3=p3->next;
            }
            
            // cout <<"a:" << a << " b:"<<b<<" c:"<<c <<" inc:"<<inc<< " p3:"<<p3->val<< endl;
            
        }
        
        
        
        return l3;
        
        
    }
};


```
