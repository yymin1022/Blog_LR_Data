[문제 바로가기](https://boj.kr/1018)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<string> map;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        map.push_back(input);
    }

    int result = 64;
    for(int i = 0; i <= N - 8; i++){
        for(int j = 0; j <= M - 8; j++){
            int tempCount = 0;
            for(int k = i; k < i + 8; k++){
                for(int l = j; l < j + 8; l++){
                    if((k % 2) ^ (l % 2)){
                        if(map[k][l] != 'B'){
                            tempCount++;
                        }
                    }else{
                        if(map[k][l] != 'W'){
                            tempCount++;
                        }
                    }
                }
            }
            result = min(result, tempCount);
            result = min(result, 64 - tempCount);
        }
    }

    cout << result << "\n";
    
    return 0;
}```