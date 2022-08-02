[문제 바로가기](https://boj.kr/13305)

```c++
#include <bits/stdc++.h>

using namespace std;

long long cost[100001];
long long dist[100001];

int main(void){
    cin.tie(NULL);
    cout.tie(NULL);
	ios_base::sync_with_stdio(false);

    int N;
	cin >> N;
	for(int i = 0; i < N - 1; i++){
        cin >> dist[i];
    }
	
    for(int i = 0; i < N; i++){
        cin >> cost[i];
    }

    long long minCost = 987654321;
    long long sumCost = 0;
    for(int i = 0; i < N - 1; i++){
		if(cost[i] < minCost){
            minCost = cost[i];
        }

		sumCost += minCost * dist[i];
	}

    cout << sumCost << "\n";

	return 0;
}```