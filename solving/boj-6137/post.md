[문제 바로가기](https://boj.kr/6137)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<char> S;
    for(int i = 0; i < N; i++) {
        char input;
        cin >> input;
        S.push_back(input);
    }

    int fromL = 0;
    int fromR = N - 1;
    string answer;
    while(fromL <= fromR){
        if((int)S[fromL] < (int)S[fromR]){
            answer += S[fromL];
            fromL++;
        }else if((int)S[fromL] > (int)S[fromR]){
            answer += S[fromR];
            fromR--;
        }else{
            int tempL = fromL;
            int tempR = fromR;

            bool isFound = false;
            while(tempL <= tempR){
                if((int)S[tempL] < (int)S[tempR]){
                    answer += S[fromL];
                    fromL++;
                    isFound = true;
                    break;
                }else if((int)S[tempL] > (int)S[tempR]){
                    answer += S[fromR];
                    fromR--;
                    isFound = true;
                    break;
                }else{
                    tempL++;
                    tempR--;
                }
            }

            if(!isFound){
                answer += S[fromL];
                fromL++;
            }
        }
    }

    for(int i = 0; i < answer.size(); i++){
        if(i && !(i % 80)){
            cout << "\n";
        }
        cout << answer[i];
    }

    return 0;
}
```