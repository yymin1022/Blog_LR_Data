[문제 바로가기](https://boj.kr/1755)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, string> A, pair<int, string> B){
    return A.second < B.second;
}

string str[10] = {
        "zero", "one", "two", "three",
        "four", "five", "six", "seven",
        "eight", "nine"
};

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> M >> N;

    vector<pair<int, string>> arr;
    for(int i = M; i <= N; i++ ){
        string tmp;
        for(auto c : to_string(i) ){
            tmp += str[c - '0'];
            tmp += " ";
        }

        arr.push_back(pair<int, string>(i, tmp));
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < arr.size(); i++){
        cout << arr[i].first << " ";
        if(i % 10 == 9){
            cout << "\n";
        }
    }

    return 0;
}
```