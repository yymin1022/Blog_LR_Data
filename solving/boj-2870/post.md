[문제 바로가기](https://boj.kr/2870)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool cmp(string A, string B){
    if(A.length() == B.length()){
        return A < B;
    }

    return A.length() < B.length();
}

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

        for(int j = 0; j < input.size(); j++){
            string num;
            while(input[j] >= '0' && input[j] <= '9'){
                num.push_back(input[j]);
                j++;
            }

            if(!num.empty()){
                string tmp;

                int k;
                for(k = 0; k < num.size(); k++){
                    if(num[k] != '0'){
                        break;
                    }
                }

                for(; k < num.size(); k++){
                    tmp.push_back(num[k]);
                }

                if(tmp.empty()){
                    tmp = "0";
                }

                arr.push_back(tmp);
            }
        }
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < arr.size(); i++){
        cout << arr[i] << "\n";
    }

    return 0;
}
```