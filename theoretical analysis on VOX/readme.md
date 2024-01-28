# Minrank Attack over Subfield for Simple VOX Parameters

## Introduction

Welcome to this Magma code repository that implements a Minrank attack against the VOX cryptosystem utilizing an intermediate field. Our work originates from a thorough theoretical analysis targeting the inherent QR structure within VOX. When the dimension parameter `c` contains a factor `c1`, the field extension within VOX allows for a non-trivial intermediate field. In these instances, public and secret keys can be interpreted as matrices over this intermediate field. Our study reveals that given `c/c1` surpasses `t/O`, we can consistently create a non-full-rank matrix from the secret key, subsequently applying the Kipnis-Shamir method to address the MinRank problem within this intermediate field.

Relative to prior MinRank attacks, our investigation specifically leverages the QR structure properties to pinpoint low-rank matrices within an intermediate field, assuming `c` is composite. The effectiveness of this attack is highlighted by its impact on the recently updated VOX parameter sets, which were thought to meet NIST security levels 1, 3, and 5, but our findings demonstrate their concrete hardness are actually 112-, 69-, and 48-bits-hard, respectively.

---

*For a detailed technical discussion of this attack, please refer to Section 4 of our associated research paper.*


## Usage

This repository provides demonstration code for a Minrank attack on the VOX cryptosystem. Users should have a working Magma environment set up and follow the instructions in the code comments to configure relevant parameters. 

```
// set simple vox parameters q, O, V, c, t
q := 251;
O := 4;
V := 5;
c := 14;
t := 5;
// set d for ks model
d := 1;
```

## Contributions & Citation

We encourage researchers and developers interested in cryptography to study, use, and contribute to this codebase. If using this project's outcomes in academic research, please adhere to appropriate citation guidelines.
