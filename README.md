#include <iostream>
using namespace std; 
#define M 10
int check[M], p[M], n, d = 0; 

void Init()
{
	for(int i = 1; i <= n; i++)
	{
		check[i] = 1; 
	}
}

void show()
{
	d++; 
	cout << endl << "Hoan vi Thu " << d << " : "; 
	for(int i = 1; i <= n; i++)
	{
		cout << p[i] << "   "; 
	}
}

void Try(int i)
{
	for(int j = 1; j <= n; j++)
	{
		if(check[j])
		{
			p[i] = j; 
			check[j] = 0; 
		}
		if(i == n)
		{
			show(); 
		}
		else
		{
			Try(i + 1);
			check[j] = 1; 
		}
	}
}

int main(int argc, char *argv[])
{
	cin >> n; 
	Init(); 
	Try(1); 
	
	
	system("pause"); 
	return 0; 
}
