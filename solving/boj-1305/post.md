[문제 바로가기](https://boj.kr/1305)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int L;
    string ad;
    cin >> L >> ad;

    int j = 0;
    vector<int> kmp(ad.length(), 0);
    for(int i = 1; i < ad.length(); i++){
        while(j && ad[i] != ad[j]){
            j = kmp[j - 1];
        }

        if(ad[i] == ad[j]) {
            j++;
            kmp[i] = j;
        }
    }

    cout << L - kmp[L - 1] << "\n";

    return 0;
}
```