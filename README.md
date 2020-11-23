# ketvirtauzd.cpp

#include <iostream>
#include <fstream>
#include <iomanip>
#include <windows.h>
#include <time.h>
using namespace std;
struct baze{string vardas; string pavarde; float vid;}; 
baze b[1000];
main() {
	ofstream rf("Rez.txt");
    ofstream rf2("vargsiukai.txt");
    ofstream rf3("galvociai.txt");
    long r1, r2;
    float v;
	string name[]={"Jonas", "Petras", "Justinas"};
	string pavarde[]={"Jonaitis", "Petraitis", "Justinaitis"};
	int pav[6]; 
	srand(time(NULL));
	
	for(long i=1; i<=1000000; i++) {
		v=0;
    r1=rand()%3; /*generacija skaiciu */ 
    rf << name[r1] << " ";
    r2=rand()%3;

     rf << pavarde[r2] << " ";
    for (long j=1; j<=5; j++) {	  pav[j]=rand()%10+1; v=v+pav[j];} 
    v=v/5;
	rf << v << endl;
	if (v<5) {rf2 << name[r1] << " " << pavarde[r2] << " " << v << endl;} else 
     	{rf3 << name[r1] << " " << pavarde[r2] << " " << v << endl;}   
 }
    
	 
	  
     

     
     
     
		
long m;
float sum=0,vid,t,med;
cout <<"iveskite eiluciu skaiciu: ";
cin >> m;
for(long i=1;i<=m;i=i+1) {
cout << "iveskite" << i << " : ";
cin >> b[i].vardas >> b[i].pavarde >> b[i].vid;
}
for(long i=1;i<=m;i=i+1) sum=sum+b[i].vid;
vid=sum/m;
cout << fixed << setprecision(2);
cout <<"vidurkis yra: " << vid << endl;


for (long j=1; j<=m-1; j++)
for (long i=1; i<=m-1; i++){
	if( b[i].vid>b[i+1].vid){
		t=b[i].vid;
		b[i].vid=b[i+1].vid;
		b[i+1].vid=t;
	}}
	if(m%2==1) med=b[(m+1)/2].vid; else med=( b[m/2].vid+b[(m/2)+1].vid )/2;
	
	cout <<"mediana yra: " << med << endl; 
	
 rf.close();
     rf2.close();
     rf3.close();
}
