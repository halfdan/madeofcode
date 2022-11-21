---
title: "Transcribing DNA Into RNA"
date: 2022-11-21T11:51:53+01:00
series: ["Rosalind"]
tags: ["python"]
---



## Problem 

We are introduced to the concept of RNA strings that are composed of an alphabet containing the letters 'A', 'C', 'G' and 'U'.

Given a DNA string `t` we are asked to transcribe it to an RNA `u` by replacing all occurences of 'T' in `t` with 'U' in `u`.

## Solution

Here I'm skipping reading from a file since we covered this in the previous exercise.

Python comes with a set of functions to modify strings. One such function is `str.replace(old, new[, count])` which returns a copy of the string `str` with all occurences of `old` replaced by `new`. 

We can trivially solve the exercise by calling this function on our input data:

```python
print(data.replace('T', 'U'))
```

