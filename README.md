# Triplet-gp-implementation-in-cpp
c++
** Find the total number of triplet geometric progression 
Input: a[]=1,16,4,16,64,16
       r=4
       
       OUTPUT: 3
       
```

#include <bits/stdc++.h>

using namespace std;
int solve(vector<int>v,int r)
{
    unordered_map<int,int>left,right;
    for(auto i:v)
    {
        right[i]++;
    }
    int n=v.size();
    int ans=0;
    for(int i=0;i<n;i++)
    {
      right[v[i]]--;
      if(v[i]%r==0)
      {
          int a=v[i]/r;
          int b=v[i];
          int c=v[i]*r;
          ans+=left[a]*right[c];
      }
      left[v[i]]++;
    }
    return ans;
}
int main()
{
   vector<int>v={1,16,4,16,64,16};
   int r=4;
   
   int n=v.size();
   
   cout<<solve(v,r);

    return 0;
}
       
