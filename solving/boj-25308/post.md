[문제 바로가기](https://boj.kr/25308)

```c++
#include <bits/stdc++.h>

using namespace std;

bool checkPoint(int);
void getPerm();

bool isVisit[8];
int cnt = 0;
vector<int> arr;
vector<int> perm;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 8; i++){
        int input;
        cin >> input;

        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());
    getPerm();

    cout << cnt << "\n";

    return 0;
}

bool checkPoint(int curIdx){
    int idxPrev = curIdx != 0 ? curIdx - 1 : 7;
    int idxNext = curIdx != 7 ? curIdx + 1 : 0;

    double cur = perm[curIdx];
    double prev = perm[idxPrev];
    double next = perm[idxNext];

    double tempX = prev / (1 + (prev / next));
    double tempY = -1 * (prev / next) * tempX + prev;
    double lineD = (tempX * tempX) + (tempY * tempY);
    double pointD = cur * cur;

    return pointD >= lineD;
}

void getPerm(){
    if(perm.size() == 8){
        bool isStrong = true;
        for(int i = 0; i < 8; i++){
            if(!checkPoint(i)){
                isStrong = false;
                break;
            }
        }

        if(isStrong){
            cnt++;
        }

        return;
    }

    for (int i = 0; i < arr.size(); i++) {
        if (!isVisit[i]) {
            isVisit[i] = true;
            perm.push_back(arr[i]);
            getPerm();
            perm.pop_back();
            isVisit[i] = false;
        }
    }
}```