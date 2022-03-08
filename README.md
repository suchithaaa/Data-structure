# Data-structure
#include<iostream>
#include<cstdlib>
using namespace std;
struct node
{
	int info;
	struct node *next;
}*start;
class single_llist
{
	public:
		node* create_node(int);
		void insert_begin();
		void insert_last();
		void insert_pos();
		void delete_begin();
		void delete_last();
		void delete_pos();
		void update_begin();
		void update_last();
		void update_pos();
		void sort();
		void reverse();
		void search();
		void display();
		single_llist()
		{
			start=NULL;
		}
	};
	int main()
	{
		int choice;
		single_llist s1,s2;
		start=NULL;
		do
		{
			cout<<"---------------"<<endl;
			cout<<"Operations on singly linked list"<<endl;
			cout<<"----------------"<<endl;
			cout<<"1.Insert at first"<<endl;
			cout<<"2.Insert at last"<<endl;
			cout<<"3.Insert at position"<<endl;
			cout<<"4.Delete at first"<<endl;
			cout<<"5.Delete at last"<<endl;
			cout<<"6.Delete at position"<<endl;
			cout<<"7.Update at first"<<endl;
			cout<<"8.Update at last"<<endl;
			cout<<"9.Update at position"<<endl;
			cout<<"10.Ascending order"<<endl;
			cout<<"11.Descending order"<<endl;
			cout<<"12.Search"<<endl;
			cout<<"13.Display"<<endl;
			cout<<"14.Exit"<<endl;
			cout<<"Enter your choice:";
			cin>>choice;
			switch(choice)
			{
				case 1:s1.insert_begin();
				s1.display();
				break;
				case 2:s1.insert_last();
				s1.display();
				break;
				case 3:s1.insert_pos();
				s1.display();
				break;
				case 4:s2.delete_begin();
				s1.display();
				break;
				case 5:s2.delete_last();
				s1.display();
				break;
				case 6:s1.delete_pos();
				s1.display();
				break;
				case 7:s1.update_begin();
				s1.display();
				break;
				case 8:s1.update_last();
				s1.display();
				break;
				case 9:s1.update_pos();
				s1.display();
				break;
				case 10:s1.sort();
				s1.display();
				break;
				case 11:s1.reverse();
				s1.display();
				break;
				case 12:s1.search();
				s1.display();
				break;
				case 13:s1.display();
				break;
				case 14:exit(0);
				break;
				default:cout<<"Wrong choice...???"<<endl;
				break;
			}
		}
		while(choice!=14);
	}
	node *single_llist::create_node(int value)
	{
		struct node *temp,*s;
		temp=new(struct node);
		if(temp==NULL)
		{
		cout<<"Memory not allocated"<<endl;
		return 0;
	}
	else
	{
		temp->info=value;
		temp->next=NULL;
		return temp;
	}
}
void single_llist::insert_begin()
{
	int value;
	cout<<"Enter the value to be inserted:";
	cin>>value;
	struct node *temp,*s;
	temp=create_node(value);
	if(start==NULL)
	{
		start=temp;
		start->next=NULL;
		cout<<temp->info<<"is inserted at first in the empty list"<<endl;
	}
	else
	{
		s=start;
		start=temp;
		start->next=s;
		cout<<temp->info<<"is inserted at first"<<endl;
	}
}
void single_llist::insert_last()
{
int value;
cout<<"Enter the value to be inserted:";
cin>>value;
struct node *temp,*s;
temp=create_node(value);
if(start==NULL)
{
	start=temp;
	start->next=NULL;
	cout<<temp->info<<"is inserted at last in the empty list"<<endl;
}
else
{
	s=start;
	while(s->next!=NULL)
	{
		s=s->next;
	}
	temp->next=NULL;
	s->next=temp;
	cout<<temp->info<<"is inserted at last"<<endl;
}
}
void single_llist::insert_pos()
{
int value,pos,counter=0,loc=1;
struct node *temp,*s,*ptr;
s=start;
while(s!=NULL)
{
s=s->next;
counter++;
}
if(counter==0){ }
else
{
	cout<<"Enter the position from"<<loc<<"to"<<counter+1<<":";
	cin>>pos;
	s=start;
	if(pos==1)
{
	cout<<"Enter the value to be inserted:";
	cin>>value;
	temp=create_node(value);
	start=temp;
	start->next=s;
	cout<<temp->info<<"is inserted at first"<<endl;
}
else if(pos>1&&pos<=counter)
{
cout<<"Enter the value to be inserted:";
cin>>value;
temp=create_node(value);
for(int i=1;i<pos;i++)
{
	ptr=s;
	s=s->next;
}
ptr->next=temp;
temp->next=s;
cout<<temp->info<<"is inserted at position"<<pos<<endl;
}
else if(pos==counter+1)
{
	cout<<"Enter the value to be inserted:";
	cin>>value;
	temp=create_node(value);
	while(s->next!=NULL)
	{
		s=s->next;
	}
	temp->next=NULL;
	s->next=temp;
	cout<<temp->info<<"is inserted at last"<<endl;
}
else
{
cout<<"Position out of range.....!!!"<<endl;
}
}
}
void single_llist::delete_begin()
{
if(start==NULL){ }
else 
{
	struct node *s,*ptr;
	s=start;
	start=s->next;
	cout<<s->info<<"deleted from first"<<endl;
	free(s);
}
}
void single_llist::delete_last()
	s=s->next;
	counter++;
}
s=start;
if(counter==1)
{
start=s->next;
cout<<s->info<<"deleted from last"<<endl;
free(s);
}
else
{
	for(i=1;i<counter;i++)
	{
	ptr=s;
	s=s->next;
}
ptr->next=s->next;
cout<<s->info<<" deleted from last"<<endl; 
 free(s); 
 } 
 } 
} 
void single_llist::delete_pos() 
{ 
 int pos, i, counter = 0, loc = 1; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
  counter++; 
 } 
 if (counter == 0){} 
 else 
 { 
 if (counter == 1) 
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 start = s->next; 
 cout<<s->info<<" deleted from first"<<endl; 
 free(s); 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 else 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 start = s->next; 
 cout<<s->info<<" deleted from first"<<endl; 
  free(s); 
 } 
 else if (pos > 1 && pos <= counter) 
 { 
 for (i = 1;i < pos;i++) 
 { 
 ptr = s; 
 s = s->next; 
 } 
 ptr->next = s->next; 
 if(pos == counter) 
 {cout<<s->info<<" deleted from last"<<endl; 
 free(s);} 
 else 
 {cout<<s->info<<" deleted from postion "<<pos<<endl; 
 free(s);} 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 } 
} 
void single_llist::update_begin() 
{ 
 int value, pos=1, i,counter = 0; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL)
 { 
 s = s->next;
 counter++; 
 } 
 if (counter == 0){} 
 else if (pos == 1) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 start->info = value; 
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; 
 } 
} 
void single_llist::update_last() 
{ 
 int value, pos, i,counter = 0; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 s=start; 
 if (counter == 0){} 
 else 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 for (i = 1; i < counter ; i++) 
 { 
 s = s->next; 
 } 
 s->info = value; 
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; 
 } 
} 
void single_llist::update_pos() 
{ 
 int value, pos, i,counter = 0, loc = 1; 
 struct node *s, *ptr; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (counter == 0){} 
 else 
 { 
 if (counter == 1) 
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
 cin>>pos; 
 s = start; 
  if (pos == 1) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 start->info = value; 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 else 
 { 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
 cin>>pos; 
 s = start; 
 if (pos == 1) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 start->info = value; 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
 } 
 else if (pos > 1 && pos <= counter) 
 { 
 cout<<"Enter the new node : "; 
 cin>>value; 
 for (i = 1; i < pos ; i++) 
 { 
  s = s->next; 
 } 
 s->info = value; 
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; 
 } 
 else 
 cout<<"Position out of range...!!!"<<endl; 
 } 
 } 
} 
void single_llist::sort() 
{ 
 struct node *ptr, *s; 
 int value; 
 if (start == NULL){} 
 else 
 { 
 ptr = start; 
 while (ptr != NULL) 
 { 
 for (s = ptr->next;s !=NULL;s = s->next) 
 { 
 if (ptr->info > s->info) 
 { 
 value = ptr->info; 
 ptr->info = s->info; 
 s->info = value; 
 } 
  } 
 ptr = ptr->next; 
 } 
 } 
} 
void single_llist::reverse() 
{ 
 struct node *ptr, *s; 
 int value; 
 if (start == NULL){} 
 else 
 { 
 ptr = start; 
 while (ptr != NULL) 
 { 
 for (s = ptr->next;s !=NULL;s = s->next) 
 { 
 if (ptr->info < s->info) 
 { 
 value = ptr->info; 
 ptr->info = s->info; 
 s->info = value;
}
 } 
 ptr=ptr->next;
}
}
}
 void single_llist::search() 
{ 
 int value, loc = 0, pos = 0, counter = 0; 
 struct node *s; 
 s = start; 
 while (s != NULL) 
 { 
 s = s->next; 
 counter++; 
 } 
 if (start == NULL){} 
 else 
 { 
 cout<<"Enter the value to be searched : "; 
 cin>>value; 
 struct node *s; 
 s = start; 
 while (s != NULL) 
 { 
 pos++; 
 if (s->info == value) 
 { 
 loc++; 
 if(loc == 1) 
 cout<<"Element "<<value<<" is found at position "<<pos; 
 else if(loc <= counter) 
 cout<<" , "<<pos; 
 } 
  s = s->next; 
 } 
 cout<<endl; 
 if (loc == 0) 
 cout<<"Element "<<value<<" not found in the list"<<endl; 
 } 
} 
void single_llist::display() 
{ 
 struct node *temp; 
 if (start == NULL) 
 cout<<"Linked list is empty...!!!"<<endl; 
 else 
 { 
 cout<<"Linked list contains : "; 
 temp = start; 
 while (temp != NULL) 
 { 
 cout<<temp->info<<" "; 
 temp = temp->next; 
 } 
 cout<<endl; 
}
}
<br>
**  output **
	![image](https://user-images.githubusercontent.com/98377715/156970297-cf3b359a-ac0d-4a0f-ad29-922c03621a30.png)
![image](https://user-images.githubusercontent.com/98377715/156970393-e50ef5ff-f383-4f05-9478-4f1bc1ebe43a.png)
![image](https://user-images.githubusercontent.com/98377715/156970474-dd95f524-6296-4d07-82c1-b41146768404.png)
![image](https://user-images.githubusercontent.com/98377715/156970543-6f706b22-e21f-4c9f-8453-8b67992299ad.png)
![image](https://user-images.githubusercontent.com/98377715/156970736-db2f4ea8-a050-4450-9206-60d8315c37f9.png)
![image](https://user-images.githubusercontent.com/98377715/156970804-a86e1d1e-d987-4841-b1ac-fff70de5f50a.png)
	![image](https://user-images.githubusercontent.com/98377715/156970879-5294ab75-5727-44c5-9a7b-077496b3dc48.png)
![image](https://user-images.githubusercontent.com/98377715/156970952-8d988332-1a78-4688-a6de-af8742de3b54.png)
	![image](https://user-images.githubusercontent.com/98377715/156971070-9173e798-0089-45f4-a7a6-6e9bb30c1384.png)
	![image](https://user-images.githubusercontent.com/98377715/156971140-f48af74e-340b-46be-b017-159b92935c8f.png)
	![image](https://user-images.githubusercontent.com/98377715/156971214-ee1e93f6-fe48-4730-949e-4e59739b82e8.png)
	![image](https://user-images.githubusercontent.com/98377715/156971277-eb3802d3-1bf0-4156-b3ce-6c0a9a541813.png)

**   linear probing**
#include<iostream>
#include<limits.h>
using namespace std;
void Insert(int ary[],int hFn, int Size)
{
int element,pos,n=0;
cout<<"Enter key element to insert\n";
cin>>element;
pos = element%hFn;
while(ary[pos]!= INT_MIN)
{
if(ary[pos]== INT_MAX)
break;
pos = (pos+1)%hFn;
n++;
if(n==Size)
break;
}
if(n==Size)
cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";
else
ary[pos] = element;
}
void display(int ary[],int Size)
{
int i;
cout<<"Index\tValue\n";
for(i=0;i<Size;i++)
cout<<i<<"\t"<<ary[i]<<"\n";
}
int main()
{
int Size,hFn,i,choice;
cout<<"Enter size of hash table\n";
cin>>Size;
hFn=Size;
int ary[Size];
for(i=0;i<Size;i++)
ary[i]=INT_MIN;
do
{
cout<<"Enter your choice\n";
cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";
cin>>choice;
switch(choice)
{
case 1: Insert(ary,hFn,Size);
break;
case 2: display(ary,Size);
break;
default: cout<<"Enter correct choice\n";
break;
}
}
while(choice);
return 0;
}
<br>
	**  output**
	![image](https://user-images.githubusercontent.com/98377715/156975572-4487f0dc-00b2-468d-9ba1-c644df24ae8d.png)

**  min heap
	#include <iostream>
#include <conio.h>
using namespace std;
void min_heap(int *a, int m, int n){
   int j, t;
   t= a[m];
   j = 2 * m;
   while (j <= n) {
      if (j < n && a[j+1] < a[j])
         j = j + 1;
      if (t < a[j])
         break;
      else if (t >= a[j]) {
         a[j/2] = a[j];
         j = 2 * j;
      }
   }
   a[j/2] = t;
   return;
}
void build_minheap(int *a, int n) {
   int k;
   for(k = n/2; k >= 1; k--) {
      min_heap(a,k,n);
   }
}
int main() {
   int n, i;
   cout<<"enter no of elements of array\n";
   cin>>n;
   int a[30];
   for (i = 1; i <= n; i++) {
      cout<<"enter element"<<" "<<(i)<<endl;
      cin>>a[i];
   }
   build_minheap(a, n);
   cout<<"Min Heap\n";
   for (i = 1; i <= n; i++) {
      cout<<a[i]<<endl;
   }
   getch();
<br>
	![image](https://user-images.githubusercontent.com/98377715/156985970-23d2bf8f-11e1-4b8d-9563-d27634a93e4a.png)

**  maxheap**
	#include <iostream>
using namespace std;
void max_heap(int *a, int m, int n) {
   int j, t;
   t = a[m];
   j = 2 * m;
   while (j <= n) {
      if (j < n && a[j+1] > a[j])
         j = j + 1;
      if (t > a[j])
         break;
      else if (t <= a[j]) {
         a[j / 2] = a[j];
         j = 2 * j;
      }
   }
   a[j/2] = t;
   return;                         
}
void build_maxheap(int *a,int n) {
   int k;
   for(k = n/2; k >= 1; k--) {
      max_heap(a,k,n);
   }
}
int main() {
   int n, i;
   cout<<"enter no of elements of array\n";
   cin>>n;
   int a[30];
   for (i = 1; i <= n; i++) {
      cout<<"enter elements"<<" "<<(i)<<endl;
      cin>>a[i];
   }
   build_maxheap(a,n);
   cout<<"Max Heap\n";
   for (i = 1; i <= n; i++) {
      cout<<a[i]<<endl;
	}
}		       
<br>
![image](https://user-images.githubusercontent.com/98377715/156986264-3a85f355-99b6-49bb-a5e7-2aaf1f1be372.png)
**  sum of sets**
	#include <iostream>
#include<limits.h>
using namespace std;
class Subset
{
	public:
		void printSum(int result[], int front, int tail)
		{
			cout << "[";
			for (int i = front; i < tail; ++i)
			{
				if (result[i] != INT_MAX)
				{
					cout << " " << result[i] << " ";
				}
			}
			cout << "]\n";
		}
	void subsetSum(int arr[], int result[], int sum, int size, int current_sum, int location)
	{
		if (location == -1)
		{
			return;
		}
		this->subsetSum(arr, result, sum, size, current_sum, location - 1);
		result[location] = arr[location];
		if (current_sum + arr[location] == sum)
		{
			this->printSum(result, location, size);
		}
		this->subsetSum(arr, result, sum, size, current_sum + arr[location], location - 1);
		result[location] = INT_MAX;
	}
	void findSubset(int arr[], int size, int sum)
	{
		if (size <= 0)
		{
			return;
		}
		int result[size];
		for (int i = 0; i < size; ++i)
		{
			result[i] = INT_MAX;
		}
		cout << "Subset Sum of 7,5,3,8,4,6,9" << " is \n";
		this->subsetSum(arr, result, sum, size, 0, size - 1);
	}
};
int main()
{
	Subset task = Subset();
	int arr[] = {
		7,5,3,8,4,6,9
	};
	int size = sizeof(arr) / sizeof(arr[0]);
	int sum =10;
	task.findSubset(arr, size, sum);
	return 0;
}
	<br>
	**  output **
![image](https://user-images.githubusercontent.com/98377715/157182840-6d790a1e-9c95-48a1-bdde-9f9e9bc7b879.png)
	
**  doubly linked list**
	#include <iostream>
using namespace std;
struct Node {
   int data;
   struct Node *prev;
   struct Node *next;
};
struct Node* head = NULL;
void insert(int newdata) {
   struct Node* newnode = (struct Node*) malloc(sizeof(struct Node));
   newnode->data = newdata;
   newnode->prev = NULL;
   newnode->next = head;
   if(head != NULL)
   head->prev = newnode ;
   head = newnode;
}
void display() {
   struct Node* ptr;
   ptr = head;
   while(ptr != NULL) {
      cout<< ptr->data <<" ";
      ptr = ptr->next;
   }
}
int main() {
   insert(3);
   insert(1);
   insert(7);
   insert(2);
   insert(9);
   cout<<"The doubly linked list is: ";
   display();
   return 0;
}
<br>
	**  output**
	![image](https://user-images.githubusercontent.com/98377715/157183140-50d14172-59bc-44c8-905b-e301863e8d3d.png)

**   splitting linked list**
	#include<iostream>
using namespace std;
struct Node
{
int value;
struct Node *next;
};
struct Node* head=NULL;
struct Node* sHead=NULL;
struct Node* temp=NULL;
void insert(int new_data)
{
struct Node* new_node = new Node();
new_node->value = new_data;
new_node->next = head;
head = new_node;
}
int n;
int ele;
int splitlndex;
int main()
{
int i;
cout<<"Enter number of elements you want in the list\t";
cin>>n;
cout<<"Enter elements:"<<endl;
for(i=0;i<n;i++)
{
cin>>ele;
insert(ele);
}
cout<<"\nList of elements:"<<endl;
Node *t;
t=head;
while(t!=NULL)
{
cout<<temp->value<<"\t";
t=t->next;
}
cout<<"\n\nEnter the element you want the list to split";
cin>>splitlndex;
while(splitlndex<0||splitlndex>n-1)
{
cout<<"Invalid position.Try again."<<endl;
cin>>splitlndex;
}
temp=head;
for(i=0;i<splitlndex;i++)
{
if(i==splitlndex-1)
{
Node *tN;
tN=temp->next;
sHead=tN;
temp->next=NULL;
break;
}
temp=temp->next;
}
temp=head;
if(temp==NULL)
{
cout<<"\n First list is empty"<<endl;
}
else
{
cout<<"\n\nFirst list element"<<endl;
while(temp!=NULL)
{
cout<<temp->value<<"\t";
temp=temp->next;
}
}
temp=sHead;
if(temp==NULL)
{
cout<<"\nSecond list is empty"<<endl;
}
else
{
cout<<"\n\nSecond list elements"<<endl;
while(temp!=NULL)
{
cout<<temp->value<<"\t";
temp=temp->next;
}
}
return 0;
}
<br>
	**  output**
![image](https://user-images.githubusercontent.com/98377715/157183491-647d9965-6890-4617-bd50-5ecdd1ad6a9a.png)
	
**  binary search tree inorder traversal**
	include<iostream>
using namespace std;
struct node {
   int data;
   struct node *left;
   struct node *right;
};
struct node *createNode(int val) 
{
   struct node *temp = (struct node *) malloc(sizeof(struct node));
   temp->data = val;
   temp->left = temp->right = NULL;
   return temp;
}
void inorder(struct node *root) {
   if (root != NULL) {
      inorder(root->left);
      cout<<root->data<<" ";
      inorder(root->right);
   }
}
struct node* insertNode(struct node* node, int val) {
   if (node == NULL) return createNode(val);
   if (val < node->data)
   node->left = insertNode(node->left, val);
   else if (val > node->data)
   node->right = insertNode(node->right, val);
   return node;
}
int main() {
   struct node *root = NULL;
   root = insertNode(root, 7);
   insertNode(root, 90);
   insertNode(root, 100);
   insertNode(root, 10);
   insertNode(root, 20);
   insertNode(root, 18);
   insertNode(root, 200);
   insertNode(root, 150);
   cout<<"In-Order traversal of the Binary Search Tree is: ";
   inorder(root);
   return 0;
}
	<br>
	**   output**
	![image](https://user-images.githubusercontent.com/98377715/157184147-7c56df65-005b-48fc-8d40-22b50e346b78.png)


