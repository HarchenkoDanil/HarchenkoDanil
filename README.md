#include <iostream>
#include <string>
#include <windows.h>
using namespace std;
int p_m(int *f, int nf, int mf)
{  
int i, j;
for(i = 0; i < nf; i++)
{
for(j = 0; j < mf; j++)
printf("%5d",*(f + i*mf + j));
cout << endl;
}
return 0;
}
int i_m(int *f, int nf, int mf)
{
int i, j;
for(i = 0; i < nf; i++)
{
for(j = 0; j < mf; j++)
cin>>*(f + i*mf + j);
}
return 0;
}
int g_m(int *f, int nf, int mf)
{
int i, j, x=0;
for(i = 0; i < nf; i++)
{
for(j = 0; j < mf; j++)
if (i==j)
{
	x=x+*(f + i*mf + j);
}
}
return x;
}
int main()
{
system("cls");
SetConsoleCP(1251);
SetConsoleOutputCP(1251);
const int n = 3, m = 3, d = 3, b = 3;
int a[n][m], g[d][b];
int i, j, s;
cout<<"ââåäûòü ÷èñëo="<<s;
cin>>s;
system("cls");
printf("Ââåä³òü ìàòðèöþ 1 a(%d,%d)\n",n,m);
i_m(&a[0][0],n,m);
system("cls");
printf("Ââåä³òü ìàòðèöþ 2 a(%d,%d)\n",n,m);
i_m(&g[0][0],d,b);
system("cls");
printf("Çàäàíà ìàòðèöÿ: 1 a(%d,%d)\n",n,m);
p_m(&a[0][0],n,m);
cout<<"ñóììà ä³àãîíàëü=="<<g_m(&a[0][0],n,m);
if (g_m(&a[0][0],n,m)>s)
{
	cout<<"  ñóìà ãîëîâî¿ ä³àãîíàë³ á³ëüøà çà ââåäåíå ÷èñëî";
}
else (cout<<"  ñóìà ãîëîâî¿ ä³àãîíàë³ ìåíøà çà ââåäåíå ÷èñëî");
printf("  Çàäàíà ìàòðèöÿ: 2 a(%d,%d)\n",n,m);
p_m(&g[0][0],d,b);
cout<<"ñóììà ä³àãîíàëü=="<<g_m(&g[0][0],d,b);
if (g_m(&g[0][0],d,b)>s)
{
	cout<<"  ñóìà ãîëîâî¿ ä³àãîíàë³ á³ëüøà çà ââåäåíå ÷èñëî";
}
else (cout<<"  ñóìà ãîëîâî¿ ä³àãîíàë³ ìåíøà çà ââåäåíå ÷èñëî");
cout     <<"="<<s;
return 0;
}
