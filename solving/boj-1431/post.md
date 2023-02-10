[문제 바로가기](https://boj.kr/1431)

```c++
#include <bits/stdc++.h>

using namespace std;

bool comp(string strA, string strB){
    int sizeA = strA.size();
    int sizeB = strB.size();

    if(sizeA != sizeB)
        return sizeA < sizeB;
    
    int numA = 0;
    int numB = 0;
    for(int i = 0; i < sizeA; i++){
        if(strA[i] >= '0' && strA[i] <= '9')
            numA += strA[i] - '0';
        if(strB[i] >= '0' && strB[i] <= '9')
            numB += strB[i] - '0';
    }
    if(numA != numB)
        return numA < numB;
    
    for(int i = 0; i < sizeA; i++){
        if(strA[i] != strB[i])
            return strA[i] < strB[i];
    }

    return true;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    vector<string> serial;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        serial.push_back(input);
    }

    sort(serial.begin(), serial.end(), comp);

    for(int i = 0; i < N; i++){
        cout << serial[i] << "\n";
    }
    
    return 0;
}
```