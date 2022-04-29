

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
}
