[문제 바로가기](https://boj.kr/2457)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> arr;
    for(int i = 0; i < N; i++){
        int A, B, C, D;
        cin >> A >> B >> C >> D;
        arr.push_back(make_pair(A * 100 + B, C * 100 + D));
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    int date = 301;
    int dateMax = 0;
    int idx = 0;
    while(date <= 1130){
        for(int i = idx; i < N; i++){
            if(arr[i].first > date){
                break;
            }

            if(arr[i].second > dateMax){
                dateMax = arr[i].second;
                idx = i;
            }
        }

        if(dateMax == date){
            cout << 0 << "\n";
            return 0;
        }else{
            date = dateMax;
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}

```
