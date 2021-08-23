---
layout: page
title: Python Decoding Challenge
description: Python puzzle hunt (2020)
img: /assets/img/pythonDecodingMsg.jpg
importance: 3
category: teaching
---

A series of fun cryptography challenges designed as a puzzle hunt to practice python programming.

Practice with: file reading, dictionaries, return values/parameters, finding and fixing bugs, and reading documentation. Assumes a basic familiarity up to the topics above in python.

I designed this for a student I was tutoring who really enjoyed puzzles. It has a bit of a storyline culminating with a final "hack".

***

<h2 class="category"> code  </h2>

<a href="https://github.com/lkmsf/pythonDecodingChallenge"> Git Repo </a>

Some code snippets: 

```python
# message1.txt

Hye! Hey you! I need yuor hlpe. I cna't eaplxin enyivrhteg now but the mgsease I sent you was cropeurdt. I'ts close but smoe of the kyes are wrong ecah "bicakte" sohlud map to "eticakb" (a sohlud be realcped by c, b -> e, ect). I'll eaplxin enyivrhteg lreta, jsut tsrut me. Oh also, I meganad to get alhod of one of the progamrs tr'ehye unisg to curport smoe of our masseesg. Hope it hslpe. Good lu!ck! 

```

```python
# theirEncodingAlg.py

#using instead of random library so it's deterministic cross platform/python version
from numpy import random 

fileName = "file.txt" 

def main():
    with open(fileName) as f: 
        origText = f.read() 
    
    encodedText = "" 
    for word in origText.split(): 
        if len(word) <= 2: 
            encodedText += word + " "
            continue 

        #shuffle inner word except for outer characters 

        #map from original index to new shuffled index 
        charMap = {} 

        #keep first letter and last letter the same 
        charMap[0] = 0 
        charMap[len(word) - 1] = len(word) - 1

        #shuffle the inner word
        random.seed(ord(word[0]) + ord(word[-1]))  #first and last letters don't change 
        randomIndecies = list(range(1, len(word) - 1)) #randomize middle indecies 
        random.shuffle(randomIndecies)

        for i in range(len(randomIndecies)): 
            charMap[i + 1] = randomIndecies[i]  #map old index to index of new letter 

        #recreate shuffled word
        for i in range(len(word)): 
            encodedText += word[charMap[i]] 
        encodedText += " "
    
    with open(fileName, "w") as f: 
        f.write(encodedText)
        

if __name__ == "__main__":
    main()
```