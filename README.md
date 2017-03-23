# asd-d-tugas-2-fajeriachmad
#ahmad_fajri_rahman
#165150301111014
#include<iostream>
using namespace std;
struct Node{
	int data;
	Node *next;};
class LinkedList{
	public:
	Node *Head;
	Node *Tail;
	void first(int simpan){
		Node *baru = new Node();
		Head = baru;
		Tail = baru;
		baru->data=simpan;
		baru->next=NULL;}
	void after(int simpan){
		Node *baru = new Node();
		baru->data=simpan;
		baru->next=Head;
		Head=baru;}
	void before(int simpan){
		Node *baru = new Node();
		Node *change = new Node();
		change=Tail;
		baru->data=simpan;
		change->next=baru;
		baru->next=NULL;
		Tail=baru;}
	void del_after(){
		Node *del = new Node();
		del = Head;
		Head = Head->next;
		delete del;}
	void del_before(){
		Node *del = new Node();
		Node *cari = new Node();
		del=Head;
		while(del!=Tail){
			cari=del;
			del=del->next;}
		cari->next=NULL;
		cari=Tail;
		delete del;}
	void print(){
		Node *baru = new Node();
		baru=Head;
		while(baru!=NULL){
			cout<<baru->data<<" -> ";
			baru=baru->next;}
		if(baru==NULL){
			cout<<"NULL";}
		cout<<endl;}};
int main(){
	LinkedList list;
	list.first(10);
	list.print();
	list.after(20);
	list.print();
	list.after(30);
	list.print();
	list.before(5);
	list.print();
	list.del_after();
	list.print();
	list.del_after();
	list.print();
	list.del_before();
	list.print();
}
