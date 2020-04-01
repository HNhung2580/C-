#include<iostream>
#include<cstring>
using namespace std;

bool palindrome(string str)
{
    int i = 0, j = str.length() - 1;
    while (i < j)
    {
        if (str[i] != str[j]) return false;
        i++, j--;
    }
    return true;
}

int main()
{
    int test;
    cin>>test;
    for(int k=0;k<test;k++)
    {
        string str;
        cin>>str;
        int i = 0, j= str.length()-1;
        int answer = -1;
        while (i < j && str[i] == str[j]) i++, j--;
        if (i < j)
        {
            string str1 = str.substr(0, i) + str.substr(i + 1, str.length() - i - 1);
            if (palindrome(str1)) 
            {
                answer = i;
            }
            
            string str2 = str.substr(0, j) + str.substr(j + 1, str.length() - j - 1);
            if (palindrome(str2))
            {
                answer= j;
            }
        }
        cout<<answer<<endl;
    }
 
    return 0;
}
           
       
