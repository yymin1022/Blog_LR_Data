[문제 바로가기](https://boj.kr/18111)

```c++
#include <bits/stdc++.h>

using namespace std;

int blockMap[501][501];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, B;
    cin >> N >> M >> B;
    
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> blockMap[i][j];
        }
    }

    int height = 0;
    int time = 214700000;

    for(int i = 0; i <= 256; i++){
        int blockAdd = 0;
        int blockRemove = 0;
        for(int j = 0; j < N; j++){
            for(int k = 0; k < M; k++){
                int curHeight = i - blockMap[j][k];
                if(curHeight < 0){
                    blockRemove -= curHeight;
                }else if(curHeight > 0){
                    blockAdd += curHeight;
                }
            }
        }

        if(blockRemove + B >= blockAdd){
            int tempTime = blockAdd + blockRemove * 2;
            if(tempTime <= time){
                height = i;
                time = tempTime;
            }
        }
    }

    cout << time << " " << height << "\n";

    return 0;
}```