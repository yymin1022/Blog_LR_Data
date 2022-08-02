[문제 바로가기](https://boj.kr/5639)

```c++
#include <bits/stdc++.h>

using namespace std;

void search(int, int);

vector<int> arr;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int input;
    while(cin >> input){
        arr.push_back(input);
    }

    arr.push_back(987654321);
    search(0, arr.size() - 1);

    return 0;
}

void search(int left, int right) {
    if(left == right){
        return;
    }

    int idx = right;
    int root = arr[left];
    for(int i = left; i < right; i++){
        if(arr[i] > root){
            idx = i;
            break;
        }
    }

    if(right - left > 1){
        search(left + 1, idx);
        search(idx, right);
    }

    cout << root << "\n";
}```