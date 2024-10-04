[문제 바로가기](https://boj.kr/1543)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> arr;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        bool check = false;
        for(int j = i + 1; j < arr.size(); j++){
            for(int k = 0; k < arr[i].size(); k++){
                if(strcmp(arr[i].c_str(), arr[j].c_str()) == 0){
                    check = true;
                    break;
                }

                arr[i].push_back(arr[i][0]);
                arr[i].erase(0, 1);
            }

            if(check){
                break;
            }
        }

        if(!check){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```