[문제 바로가기](https://boj.kr/18870)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> numsComp(N);
    vector<int> numsOrig(N);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        numsComp[i] = input;
        numsOrig[i] = input;
    }
    
    sort(numsComp.begin(), numsComp.end());
    numsComp.erase(unique(numsComp.begin(), numsComp.end()), numsComp.end());

    for(int i = 0; i < N; i++){
        cout << lower_bound(numsComp.begin(), numsComp.end(), numsOrig[i]) - numsComp.begin() << " ";
    }

    return 0;
}```