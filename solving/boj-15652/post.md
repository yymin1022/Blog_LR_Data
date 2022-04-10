[문제 바로가기](https://boj.kr/15652)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, M;
bool selected[9];

vector<int> selectedNum;
void search(int count){
    if(count == M){
        for(int i = 0; i < selectedNum.size(); i++){
            cout << selectedNum[i] << " ";
        }
        cout << "\n";
        return;
    }

    for(int i = 1; i <= N; i++){
        if(selectedNum.empty() || selectedNum.back() <= i){
            selected[i] = true;
            selectedNum.push_back(i);
            search(count + 1);
            selected[i] = false;
            selectedNum.pop_back();
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    search(0);

    return 0;
}
```