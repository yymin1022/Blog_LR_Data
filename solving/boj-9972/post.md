[문제 바로가기](https://boj.kr/9972)

```c++
#include  <bits/stdc++.h>

using namespace std;

void left(int);
void right(int);
void rotateU(int);
void rotateD(int);
void rotateF(int);
void rotateB(int);
void rotateL(int);
void rotateR(int);

char tmpCube[3][3];
char cube[6][3][3];
string temp;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string isStart;

    cin >> isStart;
    while(isStart == "START"){
        for(int i = 0; i < 3; i++){
            for(int j = 0; j < 3; j++){
                cin >> cube[0][i][j];
            }
        }

        for(int i = 0; i < 3; i++){
            for(int j = 0; j < 12; j++){
                if(j < 3){
                    cin >> cube[4][i][j];
                }else if(j < 6){
                    cin >> cube[2][i][j - 3];
                }else if(j < 9){
                    cin >> cube[5][i][j - 6];
                }else{
                    cin >> cube[3][i][j - 9];
                }
            }
        }

        for(int i = 0; i < 3; i++){
            for(int j = 0; j < 3; j++){
                cin >> cube[1][i][j];
            }
        }

        string side, direction;

        cin >> side;
        while(side != "END"){
            cin >> direction;

            if(side == "top"){
                if(direction == "right"){
                    right(0);
                    rotateU(0);
                }else{
                    left(0);
                    rotateD(0);
                }
            }else if(side == "bottom"){
                if(direction == "left"){
                    left(1);
                    rotateU(2);
                }else{
                    right(1);
                    rotateD(2);
                }
            }else if(side == "front"){
                if(direction == "right"){
                    right(2);
                    rotateF(2);
                }else{
                    left(2);
                    rotateB(2);
                }
            }else if(side == "back"){
                if(direction == "left"){
                    left(3);
                    rotateF(0);
                }else{
                    right(3);
                    rotateB(0);
                }
            }else if(side == "left"){
                if(direction == "right"){
                    right(4);
                    rotateL(0);
                }else{
                    left(4);
                    rotateR(0);
                }
            }else if(side == "right"){
                if(direction == "left"){
                    left(5);
                    rotateL(2);
                }else{
                    right(5);
                    rotateR(2);
                }
            }

            cin >> side;
        }

        bool isCorrect = true;
        for(int i = 0; i < 6; i++){
            for(int j = 0; j < 3; j++){
                for(int k = 0; k < 3; k++){
                    if(cube[i][j][k] != cube[i][0][0]){
                        cout << "No" << "\n";
                        isCorrect = false;
                        i = 6;
                        j = 3;
                        k = 3;
                    }
                }
            }
        }

        if(isCorrect){
            cout << "Yes" << "\n";
        }

        cin >> isStart;
    }
    
    return 0;
}

void left(int d){
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            tmpCube[i][j] = cube[d][i][j];
        }
    }

    cube[d][0][0] = tmpCube[0][2];
    cube[d][0][1] = tmpCube[1][2];
    cube[d][0][2] = tmpCube[2][2];
    cube[d][1][0] = tmpCube[0][1];
    cube[d][1][2] = tmpCube[2][1];
    cube[d][2][0] = tmpCube[0][0];
    cube[d][2][1] = tmpCube[1][0];
    cube[d][2][2] = tmpCube[2][0];
}

void right(int d){
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            tmpCube[i][j] = cube[d][i][j];
        }
    }

    cube[d][0][0] = tmpCube[2][0];
    cube[d][0][1] = tmpCube[1][0];
    cube[d][0][2] = tmpCube[0][0];
    cube[d][1][0] = tmpCube[2][1];
    cube[d][1][2] = tmpCube[0][1];
    cube[d][2][0] = tmpCube[2][2];
    cube[d][2][1] = tmpCube[1][2];
    cube[d][2][2] = tmpCube[0][2];
}

void rotateU(int k){
    for(int i = 0; i < 3; i++){
        temp[i] = cube[4][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[4][k][i] = cube[2][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[2][k][i] = cube[5][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[5][k][i] = cube[3][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[3][k][i] = temp[i];
    }
}

void rotateD(int k){
    for(int i = 0; i < 3; i++){
        temp[i] = cube[4][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[4][k][i] = cube[3][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[3][k][i] = cube[5][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[5][k][i] = cube[2][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[2][k][i] = temp[i];
    }
}

void rotateF(int k){
    int j = !k ? 2 : 0;

    for(int i = 0; i < 3; i++){
        temp[i] = cube[0][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[0][k][i] = cube[4][2 - i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[4][i][k] = cube[1][j][i];
    }
    for(int i = 0; i < 3; i++){
        cube[1][j][i] = cube[5][2 - i][j];
    }
    for(int i = 0; i < 3; i++){
        cube[5][i][j] = temp[i];
    }
}

void rotateB(int k){
    int j = !k ? 2 : 0;

    for(int i = 0; i < 3; i++){
        temp[i] = cube[0][k][i];
    }
    for(int i = 0; i < 3; i++){
        cube[0][k][i] = cube[5][i][j];
    }
    for(int i = 0; i < 3; i++){
        cube[5][i][j] = cube[1][j][2 - i];
    }
    for(int i = 0; i < 3; i++){
        cube[1][j][i] = cube[4][i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[4][i][k] = temp[2 - i];
    }
}

void rotateL(int k){
    int j = !k ? 2 : 0;

    for(int i = 0; i < 3; i++){
        temp[i] = cube[0][i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[0][i][k] = cube[3][2 - i][j];
    }
    for(int i = 0; i < 3; i++){
        cube[3][i][j] = cube[1][2 - i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[1][i][k] = cube[2][i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[2][i][k] = temp[i];
    }
}

void rotateR(int k){
    int j = !k ? 2 : 0;

    for(int i = 0; i < 3; i++){
        temp[i] = cube[0][i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[0][i][k] = cube[2][i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[2][i][k] = cube[1][i][k];
    }
    for(int i = 0; i < 3; i++){
        cube[1][i][k] = cube[3][2 - i][j];
    }
    for(int i = 0; i < 3; i++){
        cube[3][i][j] = temp[2 - i];
    }
}
```