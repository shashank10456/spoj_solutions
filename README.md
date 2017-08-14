#include<bits/stdc++.h>
using namespace std;
typedef long long ll;

int main()
{
    ll t,n,mx=0;
    cin>>t;
    while(t--)
    {
        cin>>n>>mx;
        ll a[n]={0};
        for(ll i=0;i<n;i++)
        {
            cin>>a[i];
        }

        ll i=0,j=0,x=0,freq=0,people,ms=0;
        bool tr=true;
        while((i<n)&&(j<n)&&(i<=j))
        {
            x+=a[j];
            if((x<=mx))
            {
                j++;
                if(tr)
                {
                    people=x;
                    tr=false;
                    ms=j-i;
                }
                if((ms<(j-i)))
                {
                    ms=j-i;
                    people=x;
                }
                else if((ms==(j-i)))
                {
                    people=min(people,x);
                }
            }
            else
            {
                x=x-a[j];

                i++;
                x=x-a[i-1];
            }
        }

        cout<<people<<" "<<ms<<endl;
    }

    return 0;
}
