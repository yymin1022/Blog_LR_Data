[문제 바로가기](https://boj.kr/12755)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int num = 1;
    string tmp;
    while(true){
        tmp = to_string(num);

        if(N <= tmp.size()){
            break;
        }

        num++;
        N -= tmp.size();
    }

    cout << tmp[N - 1] << "\n";

    return 0;
}

```