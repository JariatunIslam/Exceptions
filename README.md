# Exceptions
#include <cmath>
#include <iostream>
#include <exception>
#include <stdexcept>
using namespace std;

//Write your code 

class Calculator{
        
        public: static int power(int n, int p ){
                int ans=1;
                if(n<0 || p<0){
                 throw std::invalid_argument("n and p should be non-negative");
                }
                for(int i=1;i<=p;i++){
                        ans*=n;
                }
                        
                return ans;
        }        
};
int main()
{
    Calculator myCalculator=Calculator();
    int T,n,p;
    cin>>T;
    while(T-->0){
      if(scanf("%d %d",&n,&p)==2){
         try{
               int ans=myCalculator.power(n,p);
               cout<<ans<<endl; 
         }
         catch(exception& e){
             cout<<e.what()<<endl;
         }
      }
    }
    
}
