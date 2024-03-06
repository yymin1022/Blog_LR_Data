[문제 바로가기](https://boj.kr/1083)

```c++
    #include <bits/stdc++.h>

    using namespace std;

    int main(){
        cin.tie(NULL);
        cout.tie(NULL);
        ios_base::sync_with_stdio(false);

        int N;
        cin >> N;

        vector<int> arr;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            arr.push_back(input);
        }

        int S;
        cin >> S;

        int cnt = 0;
        for(int i = 0; i < N; i++){
            if(S == 0){
                break;
            }

            int maxIdx = i;
            int maxNum = arr[i];
            for(int j = i + 1; j < N && j <= i + S; j++){
                if(maxNum < arr[j]){
                    maxIdx = j;
                    maxNum = arr[j];
                }
            }

            for(int j = maxIdx; j > i; j--){
                int tmp = arr[j - 1];
                arr[j - 1] = arr[j];
                arr[j] = tmp;
                S--;
            }
        }

        for(int i = 0; i < N; i++){
            cout << arr[i] << " ";
        }

        return 0;
    }
```