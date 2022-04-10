[문제 바로가기](https://boj.kr/1991)

```c++
#include <bits/stdc++.h>

using namespace std;

void inOrder(int);
void postOrder(int);
void preOrder(int);

vector<pair<int, int>> tree(27);

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        char root, left, right;
        cin >> root >> left >> right;
        tree[root - 'A'] = make_pair(left - 'A', right - 'A');
    }

    preOrder(0);
    cout << "\n";
    inOrder(0);
    cout << "\n";
    postOrder(0);
    cout << "\n";

    return 0;
}

void inOrder(int root){
    int left = tree[root].first;
    int right = tree[root].second;

    if(left > 0){
        inOrder(left);
    }
    cout << (char)(root + 'A');
    if(right > 0){
        inOrder(right);
    }
}

void postOrder(int root){
    int left = tree[root].first;
    int right = tree[root].second;

    if(left > 0){
        postOrder(left);
    }
    if(right > 0){
        postOrder(right);
    }
    cout << (char)(root + 'A');
}

void preOrder(int root){
    int left = tree[root].first;
    int right = tree[root].second;

    cout << (char)(root + 'A');
    if(left > 0){
        preOrder(left);
    }
    if(right > 0){
        preOrder(right);
    }
}
```