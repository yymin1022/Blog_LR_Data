[문제 바로가기](https://boj.kr/17298)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    vector<int> A;
    for(int i = 0; i < N; i++){
        int num;
        cin >> num;
        A.push_back(num);
    }

    stack<int> numStack;
    vector<int> answer;
    for(int i = N - 1; i >= 0; i--){
        while(!numStack.empty() && numStack.top() <= A[i]){
            numStack.pop();
        }

        if(numStack.empty()){
            answer.push_back(-1);
        }else{
            answer.push_back(numStack.top());
        }

        numStack.push(A[i]);
    }
    
    for(int i = answer.size() - 1; i >= 0; i--){
        cout << answer[i] << " ";
    }

    return 0;
}```