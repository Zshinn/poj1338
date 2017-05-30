# 
#include <iostream>
using namespace std;
#include <string.h>


int min(int a,int b,int c)
{
	int min;
	min=a>b?b:a;
	return min>c?c:min;
}

int main()
{
	int ugly[1502];
	memset(ugly,0,sizeof(ugly));
	ugly[0]=1;
	int p2=0,p3=0,p5=0;
	for(int i=1;i<1502;i++)
	{
		ugly[i]=min(ugly[p2]*2,ugly[p3]*3,ugly[p5]*5);
		if(ugly[i]==ugly[p2]*2) ++p2;
		if(ugly[i]==ugly[p3]*3) ++p3;
		if(ugly[i]==ugly[p5]*5) ++p5;

	}
	int q;
	while(cin>>q&&q!=0)
	{
		cout<<ugly[q-1]<<endl;
	}
	return 0;
}
