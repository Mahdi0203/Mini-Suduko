#include<bits/stdc++.h>
using namespace std;
int main()
{
    cout<<"--Let's play a Mini Suduko Game--"<<endl;
    cout<<"\nIndex of elements:                      Rules:"<<endl;
    cout<<"a(1,1)  a(1,2)  a(1,3)  a(1,4)          1. Every 2x2 square should have unique elements."<<endl;
    cout<<"a(2,1)  a(2,2)  a(2,3)  a(2,4)          2. Every line(Horizontal or Vertical) should have unique elements."<<endl;
    cout<<"a(3,1)  a(3,2)  a(3,3)  a(3,4)\na(4,1)  a(4,2)  a(4,3)  a(4,4)\n";
    cout<<"\nInitial Suduko->\n\n ~~~~~~~~~~~~\n|3  0 | 0  0|\n|0  0 | 2  0|\n ~~~~~~~~~~~~\n|4  0 | 0  0|\n|0  1 | 0  0|\n ~~~~~~~~~~~~"<<endl;

    int n,m,need_elmnts=12,num;
    int suduko[4][4];
    suduko[0][0]=3,suduko[0][1]=0,suduko[0][2]=0,suduko[0][3]=0;
    suduko[1][0]=0,suduko[1][1]=0,suduko[1][2]=2,suduko[1][3]=0;
    suduko[2][0]=4,suduko[2][1]=0,suduko[2][2]=0,suduko[2][3]=0;
    suduko[3][0]=0,suduko[3][1]=1,suduko[3][2]=0,suduko[3][3]=0;
    while(need_elmnts!=0){
        cout<<"Enter the index of following number: ";
        cin>>n>>m;
        cout<<"Enter the number: ";
        cin>>num;
        int cnt=0;
        if(suduko[n-1][0]==num || suduko[n-1][1]==num || suduko[n-1][2]==num || suduko[n-1][3]==num ) cnt++;

        if(suduko[0][m-1]==num || suduko[1][m-1]==num || suduko[2][m-1]==num || suduko[3][m-1]==num ) cnt++;

        if(cnt==0){
            suduko[n-1][m-1]=num;
            need_elmnts--;
            for(int i=0; i<4; i++){
                for(int j=0; j<4; j++){cout<<suduko[i][j]<<"  ";
                }cout<<endl;
            }
        }
        else{
            cout<<"\nwrong number\n"<<endl;
        }
        if(need_elmnts==0) cout<<"Hurray!! You Win"<<endl;

    }

}
