[문제 바로가기](https://boj.kr/9575)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<int> arrA;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            arrA.push_back(input);
        }

        cin >> N;
        vector<int> arrB;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            arrB.push_back(input);
        }

        cin >> N;
        vector<int> arrC;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            arrC.push_back(input);
        }

        set<int> ans;
        for(int i = 0; i < arrA.size(); i++){
            for(int j = 0; j < arrB.size(); j++){
                for(int k = 0; k < arrC.size(); k++){
                    int sum = arrA[i] + arrB[j] + arrC[k];
                    string tmp = to_string(sum);

                    bool flag = true;
                    for(int h = 0; h < tmp.size(); h++){
                        if(tmp[h] != '5' && tmp[h] != '8'){
                            flag = false;
                            break;
                        }
                    }

                    if(flag){
                        ans.insert(sum);
                    }
                }
            }
        }

        cout << ans.size() << "\n";
    }

    return 0;
}s
```