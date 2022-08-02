[문제 바로가기](https://boj.kr/17479)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C;
    cin >> A >> B >> C;

    map<string, long long> normal;
    for(int i = 0; i < A; i++){
        string menu;
        long long cost;
        cin >> menu >> cost;
        normal.insert({menu, cost});
    }
    map<string, long long> special;
    for(int i = 0; i < B; i++){
        string menu;
        long long cost;
        cin >> menu >> cost;
        special.insert({menu, cost});
    }
    map<string, long long> service;
    for(int i = 0; i < C; i++){
        string menu;
        cin >> menu;
        service.insert({menu, 0});
    }

    int N;
    cin >> N;

    bool isServiced = false;
    bool isSpecialed = false;
    long long normalCost = 0;
    long long totalCost = 0;
    for(int i = 0; i < N; i++){
        string menu;
        cin >> menu;

        if(normal.find(menu) != normal.end()){
            normalCost += normal[menu];
            totalCost += normal[menu];
        }else if(special.find(menu) != special.end()){
            isSpecialed = true;
            totalCost += special[menu];
        }else if(service.find(menu) != service.end()){
            if(isServiced){
               cout << "No" << "\n";
               return 0;
            }
            isServiced = true;
        }
    }

    if(isSpecialed && normalCost < 20000){
        cout << "No" << "\n";
        return 0;
    }else if(isServiced && totalCost < 50000){
        cout << "No" << "\n";
        return 0;
    }

    cout << "Okay" << "\n";

    return 0;
}```