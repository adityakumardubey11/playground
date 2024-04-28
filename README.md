GFG POTD Solution (Remove every kth node) 29 / 04 /2024 

// java 
class Solution
{
    
    Node delete(Node head, int k) {
        if (head == null)
            return null;
        int count = 1;
        Node temp = head;
        Node back;

        if (k == 1)
            return null;

        while (temp.next != null) {
            count++;
            back = temp;
            temp = temp.next;

            if (count == k) {
                
                if (temp.next == null) {
                    back.next = null;
                    return head;
                }
                
                Node r = temp.next;
                back.next = r;
                temp = r;
                count = 1;
            }
        }
        return head;
    }
}
// c++
class Solution {
    public:
    Node * deleteK(Node *head,int K){
       if(head==NULL) 
        return NULL;
       
       Node *temp = head; 
       Node *back; 
       int kount = 1; 
       
       if(K==1) // if the given value of K is 1, it will always result in an empty list
        return NULL;
       
       while(temp!=NULL and temp->next) // traverse the list until the end or last node
       {
           kount++; // increment the counter
           back = temp; // update the previous node
           temp = temp->next; // move to the next node
           
           if(kount==K) // if the counter equals the given value of K
           {
               Node *r = temp->next; // create a pointer to the next node
               free(temp); // delete the current node
               back->next = r; // update the link between the previous and next node
               temp = r; // update the current node
               kount=1; // reset the counter
           }
           
       }
       return head; // return the modified list
    }
};



// python 3 code
def deleteK(self, head, k):
        #code here

        #if the head is None, return None
        if head is None:
            return None

        #initialize temp and back
        temp, back = head, None
        n = 1

        #if k is 1, return None
        if k == 1:
            return None

        while temp != None and temp.next != None:
            #increment n and update back
            n += 1
            back = temp
            temp = temp.next

            #if n is equal to k
            if n == k:
                #delete the current node and update back and temp
                r = temp.next
                del temp
                back.next = r
                temp = r
                n = 1
        #return the head
        return head
