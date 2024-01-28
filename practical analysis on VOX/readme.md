# Concatenated MinRank Attack for VOX parameters

## Introduction

This Magma code repository implements a MinRank attack against the VOX cryptosystem using concatenation of rectangular MinRank attack matrices. 
Our work originates from the question whether it is possible to use rectangular MinRank attack against the updated recommended parameters of VOX. 
The rectangular MinRank attack introduced by Furue and Ikematsu does not work because the submitters require that `O <= t` where `O` is the number of oil variables and `t` is that of random quadratic polynomials in VOX's public key, resulting in the matrix deformation of central map all being full rank.
However we find that a vertical concatenation of two such matrices will have rank at most `2V+t` which is smaller than `2(V+O)` when `2O > t`, where `V` is the number of vinegar variables.
Such condition allows us to create a new MinRank instance of block matrices where each block can be constructed from public key matrices. The MinRank instance is then solved by using Kipnis-Shamir method and Groebner basis technique.

We conduct the experiment on a server with a 2.40GHz Intel(R) Xeon(R) Silver 4214R CPU and 32GB RAM. The effectiveness of this attack is surprising, with 6 of 9 recommended VOX parameters attacked using less than two seconds, 8 of 9 attacked using less than one minute.

|  λ  |  q  |  O  |  V  |  c  |  t  | Running time (second) | Total Memory Usage (MB) |
| --- | --- | --- | --- | --- | --- | --------------------- | ----------------------- |
| 128 | 251 |  4  |  5  | 13  |  6  |          0.170        |           32.09         |
| 128 | 251 |  5  |  6  | 11  |  6  |          0.510        |           32.09         |
| 128 | 251 |  6  |  7  |  9  |  6  |      27357.799        |         6147.06         |
| 192 |1021 |  5  |  6  | 15  |  7  |          0.440        |           32.09         |
| 192 |1021 |  6  |  7  | 13  |  7  |          0.790        |           32.09         |
| 192 |1021 |  7  |  8  | 11  |  7  |         26.170        |          157.69         |
| 256 |4093 |  6  |  7  | 17  |  8  |          1.240        |           64.12         |
| 256 |4093 |  7  |  8  | 14  |  8  |          1.870        |           64.12         |   
| 256 |4093 |  8  |  9  | 13  |  8  |         51.530        |          256.00         |

---

*For a detailed technical discussion of this attack, please refer to Section 3 of our associated research paper.*

## Usage

This repository provides demonstration code for a Minrank attack on the VOX cryptosystem. Users should have a working Magma environment set up and follow the instructions in the code comments to configure relevant parameters. 

```
// parameters for VOX
q := 251;
O := 6;
V := 7;
c := 9;
t := 6;
```

## Contributions & Citation

We encourage researchers and developers interested in cryptography to study, use, and contribute to this codebase. If using this project's outcomes in academic research, please adhere to appropriate citation guidelines.