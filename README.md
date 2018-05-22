# CPlusPlus

#include <cstdlib>
#include <iostream>
#include <string>
#include <cmath>
#include <sstream>

using namespace std;


int main()
{
	int t, A, B, suma=0;
	int tab[200000];
	string liczba, odwrocona;
	stringstream ss;
	
	do{
		cin>>t;
	}while(t<1 || t>200000);
	
	for(int i=0;i<t;i++)
	{
		cin>>A>>B;
		if(A<1 || A>B || B>pow(10, 25))   //sprawdzanie A i B
		{
			break;
		}
		
		for(int j=A;j<=B;j++)
		{
			
			ss << j;
			liczba = ss.str(); // NIE MAM POJECIA JAK USUNAC ZAWARTOSC
			
			ss.clear();
			ss.str("");
			
			cout<<liczba<<endl;
			
			int dlugosc = liczba.length();
			
			for(int k=0; k<dlugosc; k++)   //odwracanie liczby
        	odwrocona+=liczba[dlugosc-k-1];
        	cout<<" "<<odwrocona<<endl;
        	
        	if(liczba == odwrocona)
        	{
        		suma=suma+1;
			}	
		}
		tab[i]=suma;
	}
	
	for(int z=0;z<t;z++)
	{
		cout<<tab[z]<<endl;
	}
	
	
	system("PAUSE");
	return 0;
}
