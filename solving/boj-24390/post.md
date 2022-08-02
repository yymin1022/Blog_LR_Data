[문제 바로가기](https://boj.kr/24390)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    string inputStr;
    cin >> inputStr;

    int M = stoi(inputStr.substr(0, 2));
    int S = stoi(inputStr.substr(3, 2));

    bool isStartBtn = false;
    int count = 0;

    if(S >= 30){
        count++;
        S -= 30;

        isStartBtn = true;
    }

    if(M >= 10){
        count += M / 10;
        M %= 10;
    }
    
    count += M;

    count += S / 10;

    if(!isStartBtn){
        count++;
    }

    cout << count;
}```