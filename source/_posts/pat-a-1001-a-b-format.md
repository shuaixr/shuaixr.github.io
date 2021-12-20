---
title: PAT 甲级 1001 A+B Format
tag: [PAT, PAT甲级]
---

Calculate a+b and output the sum in standard format -- that is, the digits must be separated into groups of three by commas (unless there are less than four digits).

### Input Specification:

Each input file contains one test case. Each case contains a pair of integers a and b where −10^6^≤a,b≤10^6^. The numbers are separated by a space.

### Output Specification:

For each test case, you should output the sum of a and b in one line. The sum must be written in the standard format.

<!--more-->

## 中文大意:

计算 a 与 b 的和并用标准格式输出，也就是用逗号分为 3 个一组（除非小于 4 位）

### 输入格式:

每个测试输入包含一个测试用例，每个测试用例包含一对整数 a 和 b (−10^6^≤a,b≤10^6^)

### 输出格式:

在一行中用标准格式输出 a 与 b 的和

## 代码:

```c++
#include <iostream>
#include <string>

using namespace std;

int main() {
    int a, b, sl;
    cin >> a >> b;
    string s = to_string(a + b);
    sl = s.length();
    for (int i = 0; i < sl; i++) {
        cout << s[i];
        if (sl - i >= 3 && (sl - i) % 3 == 1 && s[i] != '-')
            cout << ',';
    }
}
```
