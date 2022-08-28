[문제 바로가기](https://boj.kr/2263)

```c++
#include  <bits/stdc++.h>

using namespace std;

void preOrder(int, int, int);

vector<int> idx(100001);
vector<int> inOrder(100001);
vector<int> postOrder(100001);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> inOrder[i];
        idx[inOrder[i]] = i;
    }

    for(int i = 0; i < N; i++){
        cin >> postOrder[i];
    }

    preOrder(0, 0, N);

    return 0;
}

void preOrder(int inFrom, int postFrom, int size){
    if(!size){
        return;
    }

    int postTo = postFrom + size - 1;
    int root = postOrder[postTo];

    cout << root << " ";

    int leftSize = idx[root] - inFrom;
    preOrder(inFrom, postFrom, leftSize);

    int rightInFrom = inFrom + leftSize + 1;
    int rightPostFrom = postFrom + leftSize;
    int rightSize = size - leftSize - 1;
    preOrder(rightInFrom, rightPostFrom, rightSize);
}
```