[문제 바로가기](https://boj.kr/26162)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isPrime[120];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 2; i < 120; i++){
        int j = i;
        while(i * j < 120){
            isPrime[i * j] = true;
            j++;
        }
    }

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        bool flag = false;
        for(int j = 2; j < 120; j++){
            for(int k = 2; k < 120; k++){
                if(j + k == input && !isPrime[j] && !isPrime[k]){
                    flag = true;
                    break;
                }
            }
            if(flag){
                break;
            }
        }

        cout << (flag ? "Yes" : "No") << "\n";
    }

    return 0;
}

```