import java.io.*;

class Linkedlist {
    Node head;
    class Node{
        int data;
        Node next;
        Node(int d){data=d;next=null;} 
    }
    public void push(int data){
        Node node=new Node(data);
        node.next=head;
        head=node;
        
    }
    public void append(int data){
        Node node=new Node(data);
         if (head == null)
        {
            head = new Node(data);
            return;
        }
        Node last;
        last=head;
        node.next=null;
        while(last.next!=null){
            last=last.next;
        }
       
        last.next=node;
        
        
    }
    public void inpos(Node prenode,int data){
        Node node=new Node(data);
          if (prenode == null)
        {
            System.out.println("The given previous node cannot be null");
            return;
        }
        node.next=prenode.next;
        prenode.next=node;
    }
    public   void print(){
        Node tnode;
        tnode=head;
        while(tnode!=null){
            System.out.print(tnode.data+ " ");
            tnode=tnode.next;
        }
    }
	public static void main (String[] args) {
          Linkedlist llist=new Linkedlist();
          llist.append(10);
          llist.push(12);
          llist.push(23);
          llist.append(56);
          llist.inpos(llist.head.next,999);
          llist.print();
	}
}

