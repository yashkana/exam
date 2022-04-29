

exam
#include<bits/stdc++.h><br>
using namespace std;<br>
class graph<br>
{<br>
	public:<br>
	map <int,bool>visited;<br>
	map<int,list<int> > adj;<br>
	void addedge(int v,int w);<br>
	void dfs(int v);	<br>
};<br>
void graph::addedge(int v,int w)<br>
{<br>
	adj[v].push_back(w);<br>
	adj[w].push_back(v);<br>
}<br>
void graph::dfs(int v)<br>
{<br>
	visited[v]=true;<br>
	cout<<v<<" ";<br>
	list<int>::iterator i;<br>
	for(i=adj[v].begin();i !=adj[v].end();i++)<br>
	{<br>
	
	if(!visited[*i])<br>
	{<br>
		dfs(*i);<br>
		
	}<br>
}<br>
}<br>
int main()<br>
{<br>
	 graph g;<br>
		g.addedge(2,0);<br>
	g.addedge(0,8);<br>
	g.addedge(8,1);<br>
	g.addedge(1,0);<br>
	g.addedge(1,2);<br>
	g.addedge(8,8);<br>
	g.dfs(2);<br>
}<br>

	
	
	
	
BINARY SEARCH TREE<br>
	#include<iostream><br>
using namespace std;<br>
class bst<br>
{<br>
	int data;<br>
	bst *left,*right;<br>
	public:bst();<br>
	bst(int);<br>
	bst*insert(bst*,int);<br>
	void inorder(bst*);<br>
};<br>
bst::bst()<br>
:data(0)<br>
,left(NULL)<br>
,right(NULL)<br>
{<br>
}<br>
bst::bst(int value)<br>
{<br>
	data=value;<br>
left=right=NULL;<br>
}<br>
bst* bst::insert(bst* root,int value)<br>
{<br>
	if(!root)<br>
	{<br>
		return new bst(value);<br>
	}<br>
	if(value>root->data)<br>
	{<br>
		root->right=insert(root->right,value);<br>
	}<br>
	else<br>
	{<br>
	
		root->left=insert(root->left,value);<br>
<br>	}<br>
	return root;<br>
}<br>
void bst::inorder(bst* root)<br>
{<br>
	if (!root) {<br>
        return;<br>
    }<br>
	inorder(root->left);<br>
	cout<<root->data<<endl;<br>
	inorder(root->right);<br>
}<br>
int main()<br>
{<br>
	bst b,*root=NULL;<br>
	root=b.insert(root,50);<br>
	b.insert(root,30);<br>
	b.insert(root,20);<br>
	b.insert(root,70);<br>
	b.insert(root,60);<br>
	b.inorder(root);<br>
	return 0;<br>
}<br>

	
	
	Merg sort
	#include<iostream><br>
using namespace std;<br>
void merge(int *a,int low,int high,int mid)<br>
{<br>
	int i,j,k,temp[high-low+1];<br>
	i=low;<br>
	j=mid+1;<br>
	k=0;<br>
	while(i<=mid && j<=high)<br>
	{
		if(a[i]<a[j])<br>
		{
			temp[k]=a[i];<br>
			i++;<br>
			k++;<br>
		}<br>
		else<br>
		{
		
		temp[k]=a[j];<br>
		i++;<br>
		k++;<br>
	}<br>
	}<br>
	while(i<=mid)<br>
	{<br>
		temp[k]=a[i];<br>
		k++;<br>
		j++;<br>
	}<br>
	while(j<=high)<br>
	{<br>
		temp[k]=a[j];<br>
		k++;<br>
		j++;<br>
	}<br>
	while(i=low && j<=high)<br>
	{<br>
		a[i]=temp[k];<br>
	}<br>

}<br>
void mergsort(int *a,int low,int high)<br>
{<br>
	int mid;<br>
	mid=(low+high)/2;<br>
	mergsort(a,low,mid);<br>
	mergsort(a,mid+1,high);<br>
	merge(a,low,high,mid);<br>
}<br>
int main()<br>
{
	int n;<br>
	cout<<"enter no of element to be sorted";<br>
	cin>>n;<br>
	int arr[n];<br>
	for(int i=0;i<n;i++)<br>
	{<br>
	cout<<"enter element"<<i+1<<endl;<br>
	cin>>arr[i];<br>
	}<br>
		mergsort(arr,0,n-1);<br>
		cout<<"sortde data";<br>

	for(int i=0;i<n;i++)<br>
				cout<<"sorted element is"<<arr[i];<br>
	
}<br>

	return 0;<br>
}<br>
