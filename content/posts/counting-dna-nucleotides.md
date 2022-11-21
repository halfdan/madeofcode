---
title: "Counting DNA Nucleotides"
date: 2022-11-20T10:54:34+01:00
series: ["Rosalind"]
tags: ["python"]
---

This is the very first problem on the website in the "Bioinformatics Stronghold" category. As expected we are starting fairly light.

## Problem

We receive a DNA string consisting of the letters A, C, G and T and are asked to count the occurrence of each letter. 

The sample dataset looks as follows:

```
AGCTTTTCATTCTGACTGCAACGGGCAATATGTCTCTGTGTGGATTAAAAAAAGAGTGTCTGATAGCAGC
```

with the solution for it being `20 12 17 21`.

## Solution

Since the dataset comes in the form of a file we first need to read it

```python 
data = open("rosalind_dna.txt").read()
```

then remove any extraneous whitespace

```python
data = data.strip()
```

and finally we can use a [defaultdict](https://docs.python.org/3/library/collections.html#collections.defaultdict) as a simple structure to store character counts.

```python
from collections import defaultdict

counts = defaultdict(int)
for ch in data:
  counts[ch] += 1

print(f"{counts['A']} {counts['C']} {counts['G']} {counts['T']}")
```

The defaultdict uses an int as a default type for missing keys and since the default for int is 0 we can `+=` on it. 

**Protip:** Instead of using a defaultdict here, Python also comes with a special `Counter` collection that is made for, well, counting things.

The code could be simplified to:

```python
from collections import Counter

data = open("rosalind_dna.txt").read()
data = data.strip()
cnt = Counter(data)
print(" ".join([str(c[k]) for k in sorted(c.keys())]))
```


