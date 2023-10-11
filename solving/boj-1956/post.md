[문제 바로가기](https://boj.kr/1956)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[401][401];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int V, E;
	cin >> V >> E;
	for(int i = 1; i <= V; i++){
		for(int j = 1; j <= V; j++){
			arr[i][j] = 987654321;
		}
	}

    for(int i = 0; i < E; i++){
		int a, b, c;
		cin >> a >> b >> c;
		arr[a][b] = c;
	}

	int ans = 987654321;
	for(int k = 1; k <= V; k++){
		for(int i = 1; i <= V; i++){
			for(int j = 1; j <= V; j++){
				if(arr[i][k] + arr[k][j] < arr[i][j]){
					arr[i][j] = arr[i][k] + arr[k][j];
				}
			}
		}
	}

	for(int i = 1; i <= V; i++){
		for(int j = 1; j <= V; j++){
			if(i != j){
    			ans = min(arr[i][j] + arr[j][i], ans);
            }
    	}
	}

	cout << (ans == 987654321 ? -1 : ans) << "\n";

    return 0;
}

```
