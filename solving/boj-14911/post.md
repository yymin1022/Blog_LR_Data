[문제 바로가기](https://boj.kr/14911)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int input;
    vector<int> arr;
    while(cin >> input){
        arr.push_back(input);
    }

    int S = arr.back();
    arr.pop_back();

    sort(arr.begin(), arr.end());

    int cnt = 0;
    map<pair<int, int>, bool> isVisit;
    for(int i = 0; i < arr.size(); i++){
        for(int j = i + 1; j < arr.size(); j++){
            if(arr[i] + arr[j] == S && !isVisit[make_pair(arr[i], arr[j])]){
                cnt++;
                isVisit[make_pair(arr[i], arr[j])] = true;

                cout << arr[i] << " ";
                cout << arr[j] << "\n";
            }
        }
    }

    cout << cnt << "\n";

    return 0;
}
```