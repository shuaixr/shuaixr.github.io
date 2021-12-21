---
title: PAT 甲级 1002 A+B for Polynomials

tag: [PAT, PAT甲级]

date: 2021-12-21 10:53:17
---

This time, you are supposed to find A+B where A and B are two polynomials.

### Input Specification:

Each input file contains one test case. Each case occupies 2 lines, and each line contains the information of a polynomial:
_K N<sub>1</sub> a<sub>N1</sub> N<sub>2</sub> a<sub>N2</sub> ... N<sub>K</sub> a<sub>NK</sub>_
where K is the number of nonzero terms in the polynomial, _N_<sub>_i_</sub> and _a<sub>Ni</sub> (i=1,2,⋯,K)_ are the exponents and coefficients, respectively. It is given that _1 ≤ K≤ 10，0 ≤ N <sub>K</sub>< ⋯ < N<sub>2 </sub> < N<sub>1</sub> ≤ 1000_.

### Output Specification:

For each test case you should output the sum of A and B in one line, with the same format as the input. Notice that there must be NO extra space at the end of each line. Please be accurate to 1 decimal place.

<!--more-->

## 中文大意:

这次，你要将 A，B 两个多项式相加

### 输入格式:

每个测试用例包含两行多项式的信息：
_K N<sub>1</sub> a<sub>N1</sub> N<sub>2</sub> a<sub>N2</sub> ... N<sub>K</sub> a<sub>NK</sub>_
其中 K 是多项式中的非零项数，_N_<sub>_i_</sub> 和 _a<sub>Ni</sub> (i=1,2,⋯,K)_ 分别是指数和系数，其中 _1 ≤ K≤ 10，0 ≤ N <sub>K</sub>< ⋯ < N<sub>2 </sub> < N<sub>1</sub> ≤ 1000_.

### 输出格式:

对于每个测试用例需要在一行中输出 A 和 B 相加的结果，格式与输入相同，结尾无空格，精确到小数点后 1 位

## 代码:

```c++
// STL yyds!!!
// 这里利用了MAP自带的排序特性

#include <bits/stdc++.h>

using namespace std;

int main() {
    int k = 0, e;
    float c;
    map<int, float> m;
    for (int i = 0; i < 2; i++) {
        scanf("%d", &k);
        for (int j = 0; j < k; j++) {
            scanf("%d%f", &e, &c);
            m[e] += c;
            if (m[e] == 0.0)
                m.erase(e);
        }
    }
    printf("%d", m.size());
    for (auto ri = m.rbegin(); ri != m.rend(); ri++) {
        printf(" %d %.1f", ri->first, ri->second);
    }

}

```
