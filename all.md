# 001 two sum


``` cpp
// cpp use map
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        map<int,int> m;
        for(int i=0;i< nums.size(); i++){
            if(m.find(target - nums[i]) != m.end()){
                return {i,m[target - nums[i]]};
            }else{
                m[ nums[i]] = i ;
            }
        }
        
        return {0,0};
    }
};
```


# 0002 add two numbers
stupid
``` cpp
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


little improve
``` cpp
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
        int inc=0,a=0,b=0,c=0 ;

        ListNode *head = new ListNode();
        ListNode *p=head;
        while(l1 or l2 or inc){  
            a=l1?l1->val:0;
            b=l2?l2->val:0;
           
            if(l1) l1=l1->next;
            if(l2) l2=l2->next;
            
            c=a+b+inc;
            inc=c/10;
            
            p->next  = new ListNode(c%10) ;
            p=p->next;
        }
        
        return head->next;
    }
};
```


