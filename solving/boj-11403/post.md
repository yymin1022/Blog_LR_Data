[문제 바로가기](https://boj.kr/11403)

```c++
#include <iostream>

using namespace std;

void floyd();

int graph[100][100];
int N;

int main(void){
    scanf("%d", &N);

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            scanf("%d", &graph[i][j]);
        }
    }

    floyd();

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            printf("%d ", graph[i][j]);
        }
        printf("\n");
    }
}

void floyd(){
    for(int k = 0; k < N; k++){
        for(int j = 0; j < N; j++){
            for(int i = 0; i < N; i++){
                if(graph[j][k] && graph[k][i]){
                    graph[j][i] = 1;
                }
            }
        }
    }
}
```