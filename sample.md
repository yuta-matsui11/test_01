# 見出し
16:50

石村のかきあげ

ああああい

```
#include <bits/stdc++.h>
using namespace std;
int main(){
  int N;
  cin >> N;
  long L[N];
  for(int i=0; i<N; i++) {
    long tmp;
    cin >> tmp;
    L[i] = tmp * 2;
  }
  
  int ans=0;
  
  for(int bit=0; bit < (1 << N); bit++){
    long now = 1;
    long last = 1;
    int count = 0;
    
    for(int i=0; i<N; i++){
      if(bit & (1<<i)) now = now + L[i];
      else now = now - L[i];
      
      if(now*last < 0) count++;
      
      last = now;
    }
    
    ans = max(ans, count);
  }
  
  cout << ans << endl;
  
}
```