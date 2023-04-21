class Node:
    '''create nodes in the linked list with attributes
        1-data
        2-address of next
    '''
    def __init__(self,data=None,next=None):
        self.data = data
        self.next=next

class LinkedList:
    '''creating the linked list using the nodes
        head - refers to the address of the first element in LL
        head is stored so that a new element can be inserted at beginning
    '''
    def __init__(self):
        self.head = None #blank linked list when self.head=None

    def insert_at_beginning(self,data):
        '''this 2 steps can be done in a single line using
            self.head = Node(data,self.head)'''
        # node = Node(data,self.head) #setting the link part to the current head
        # self.head=node #node contains the address of the object (node object itself)
        self.head = Node(data,self.head)

    def print(self):
        if self.head is None:
            print('empty')
            return
        itr  = self.head # address of a 1st node(it is a node object)->starting traversal
        llstr = ''
        while itr:
            llstr+=str(itr.data)+ '-->'
            itr=itr.next
        print(llstr)
    def insert_at_end(self,data):
        if self.head is None: #exception: head is none when the LL is blank
            self.head=Node(data,None) #create a new node and store it in head
            return
        '''in a linked list to insert at the end we need to traverse till the end'''
        itr=self.head
        while itr.next: #exits from this while when the next is none-> ie: the end
            itr = itr.next
        itr.next = Node(data,None) #creates a new node and adds the address of the new node in the next of prev node--> linking
            
    def insert_values(self,data_list):#inserting list of values at the end
        '''to insert a list of values'''
        for data in data_list:
            self.insert_at_end(data)

    def find_len(self):
        count=0
        itr = self.head
        if itr is None:
            print('zero')
            return
        while itr:
            count+=1
            itr=itr.next
        return count

    def remove_at(self,idx):
        '''valid index?'''
        if idx<0 or idx>=self.find_len():
            raise Exception('not valid index')
        
        '''removing element at the head --> O(1)'''
        if idx==0:
            self.head = self.head.next #setting the link part to the next element
            return


        '''at any other index'''
        count = 0
        itr = self.head
        while itr:
            
            if count==idx-1:
                itr.next=itr.next.next #skipping an element
                break
            itr=itr.next
            count+=1
    def insert_at(self,idx,data):
        if idx==0:
            self.insert_at_beginning(data)
            return
        if idx== self.find_len():
            self.insert_at_end(data)
            return
        count = 0
        itr = self.head
        while itr:  
            if count==idx-1: #stopping one before
                itr.next=Node(data,itr.next) #adding new node and setting data of new node as the next link
                break
            itr=itr.next
            count+=1


if __name__=='__main__':
    ll=LinkedList()
    #ll.find_len()
    # ll.print()
    # ll.insert_at_beginning(5)
    # ll.insert_at_beginning(89)
    # ll.print()
    # ll.insert_at_end(25)
    # ll.print()
    # ll.insert_at_end(332)
    ll.insert_at_beginning(1)
    # ll.print()
    ll.insert_values(['amal','anagha','samod'])
    ll.print()
    print(ll.find_len())
    ll.remove_at(2)
    ll.print()
    ll.insert_at(3,'preesha')
    ll.print()
    ll.insert_at(2, 'adopted')
    ll.print()
    ll.insert_at(5, 'final')
    ll.print()
