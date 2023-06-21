#include<iostream>
using namespace std;
class node
{
public:
	int data;
	node* next;
	node* prev;
	node(int val)
	{
		data = val;
		next = NULL;
		prev = NULL;
	}
};
void insertAtFirst(node*& head, int val)
{
	node* newnode = new node(val);
	newnode->next = head;
	head = newnode;

}
void insertAtLast(node*& head, int val)
{
	node* newnode = new node(val);
	node* temp = head;
	if (head == NULL)
	{
		head = newnode;
		return;
	}
	while (temp->next != NULL)
	{
		temp = temp->next;
	}
	temp->next = newnode;
}
void display(node* head)

{
	while (head != NULL)
	{
		cout << head->data << "->";
		head = head->next;
	}
cout<<"NULL"<<endl;
}
bool search(node* head, int key)
{
    node*temp=head;
	while (temp != NULL)
	{
	    if(temp->data==key){
	        return true;
	    }
		temp = temp->next;
	   	
	}
	return false; 

}
int main()
{
	node* head ;
	insertAtFirst(head, 11);
	insertAtFirst(head, 9);
	insertAtFirst(head, 4);
	insertAtLast(head, 1);
	insertAtLast(head, 2);
	insertAtLast(head, 3);
	cout<<search(head,3)<<endl;
	display(head);

	return 0;
}
