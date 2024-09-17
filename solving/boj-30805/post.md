[문제 바로가기](https://boj.kr/30805)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B) {
    if(A.first == B.first){
        return A.second < B.second;
    }

    return A.first > B.first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> A;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        A.push_back(make_pair(input, i));
    }

    int M;
    cin >> M;

    vector<pair<int, int>> B;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        B.push_back(make_pair(input, i));
    }

    sort(A.begin(), A.end(), cmp);
    sort(B.begin(), B.end(), cmp);

    vector<int> ans;
    int idxA = 0;
    int idxB = 0;
    int limitA = 0;
    int limitB = 0;
    while(idxA < N && idxB < M){
        if(A[idxA].first == B[idxB].first){
            if(limitA > A[idxA].second){
                idxA++;
            }else if(limitB > B[idxB].second){
                idxB++;
            }else{
                limitA = A[idxA].second;
                limitB = B[idxB].second;
                ans.push_back(A[idxA].first);
                idxA++;
                idxB++;
            }
        }else if(A[idxA].first > B[idxB].first){
            idxA++;
        }else{
            idxB++;
        }
    }

    cout << ans.size() << "\n";
    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << " ";
    }

    return 0;
}
```
