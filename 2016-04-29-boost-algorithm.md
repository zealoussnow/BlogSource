---
title: Boost学习 —— algorithm
date: 2016-04-29 17:36:10
categories:
- 程序设计
tags:
- C++ Boost
permalink: boost-algorithm
---

## Searching Algorithms

### Boyer-Moore Search(boyer_moore.hpp)

(1). Interface

For flexibility, the Boyer-Moore algorithm has two interfaces:

<!-- more -->

* A object-based interface

```cpp
    template<typename patIter>
    class boyer_moore {
    public:
        boyer_moore(patIter first, patIter last);
        ~boyter_moore();

        template<typename corpusIter>
        corpusIter operator()(corpusIter corpus_first, corpusIter corpus_last);
    };
```

* A procedural one

```cpp
    template<typename patIter, typename corpusIter>
    corpusIter boyer_moore_search(
        corpusIter corpus_first, corpusIter corpus_last,
        patIter first, patIter last);
```

(2). Performance

(3). Memory Use

The algorithm allocates two internal tables

* The first one is proportional to the length of the pattern
* The second one has one entry for each member of the "alphabet"
in the pattern. For (8-bit) character types, this table contains 256 entries.