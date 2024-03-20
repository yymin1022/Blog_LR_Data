[문제 바로가기](https://boj.kr/1655)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    priority_queue<int> pqMax;
    priority_queue<int, vector<int>, greater<int>> pqMin;

    int input;
    cin >> input;
    pqMax.push(input);
    cout << pqMax.top() << "\n";

    cin >> input;
    if(input > pqMax.top()){
        pqMin.push(input);
    }else{
        pqMin.push(pqMax.top());
        pqMax.pop();
        pqMax.push(input);
    }
    cout << pqMax.top() << "\n";

    for(int i = 2; i < N; i++){
		cin >> input;

        pqMax.push(input);

        if(pqMax.top() > pqMin.top()){
            pqMax.pop();
            pqMin.push(input);

            if(pqMin.size() > pqMax.size()){
                pqMax.push(pqMin.top());
                pqMin.pop();
            }
        }
        if(pqMax.size() - pqMin.size() > 1){
            pqMin.push(pqMax.top());
            pqMax.pop();
        }

		cout << pqMax.top() << "\n";
	}

    return 0;
}
```
