[문제 바로가기](https://boj.kr/16506)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    map<string, pair<string, bool>> assembly;
    assembly["ADD"] = make_pair("00000", false);
    assembly["ADDC"] = make_pair("00001", true);
    assembly["SUB"] = make_pair("00010", false);
    assembly["SUBC"] = make_pair("00011", true);
    assembly["MOV"] = make_pair("00100", false);
    assembly["MOVC"] = make_pair("00101", true);
    assembly["AND"] = make_pair("00110", false);
    assembly["ANDC"] = make_pair("00111", true);
    assembly["OR"] = make_pair("01000", false);
    assembly["ORC"] = make_pair("01001", true);
    assembly["NOT"] = make_pair("01010", false);
    assembly["MULT"] = make_pair("01100", false);
    assembly["MULTC"] = make_pair("01101", true);
    assembly["LSFTL"] = make_pair("01110", false);
    assembly["LSFTLC"] = make_pair("01111", true);
    assembly["LSFTR"] = make_pair("10000", false);
    assembly["LSFTRC"] = make_pair("10001", true);
    assembly["ASFTR"] = make_pair("10010", false);
    assembly["ASFTRC"] = make_pair("10011", true);
    assembly["RL"] = make_pair("10100", false);
    assembly["RLC"] = make_pair("10101", true);
    assembly["RR"] = make_pair("10110", false);
    assembly["RRC"] = make_pair("10111", true);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        string cmd;
        int rD, rA, rB;
        cin >> cmd >> rD >> rA >> rB;

        string ans = "";
        ans += assembly[cmd].first;
        ans += "0";
        ans += bitset<3>(rD).to_string();
        ans += bitset<3>(rA).to_string();

        if(assembly[cmd].second){
            ans += bitset<4>(rB).to_string();
        }else{
            ans += bitset<3>(rB).to_string();
            ans += "0";
        }

        cout << ans << "\n";
    }

    return 0;
}
```