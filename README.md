# cpp-cheatsheet
snippets for cpp competitive programming

[link to repo](https://github.com/ashish1729/cpp-cheatsheet)

## Older version

[version 1](https://ashish1729.github.io/cpp-cheatsheet/README_old)

## Binary
``` cpp
a + ~a = -1; // it sets all 1s
-a = 1 + ~a; // can be easily derived using a + -a = 1 + -1 . and replace -1 from previous

(a|b) + (a&b) = a + b;
a^b = (a - (a&b)) + (b - (a&b));  // bits of a which are not in b + bits of b which are not in a
a^b = a + b - 2 * (a&b); // simplifying last line
a^b = (a|b) - (a&b);     // using value of a + b from above , easy to see in venn diagram also , because xor is symmetric difference

some other equations at [codeforce blog](https://codeforces.com/blog/entry/94470)
```

## Multinomial to binomial formula 

<img width="557" height="48" alt="image" src="https://github.com/user-attachments/assets/dc3ed98d-314c-4c0b-ab19-087311f9f1e3" />



```math
\frac{(C_{1} + C_{2} + ... + C_{N})!}{C_{1}! C_{2}! ... C_{N}!} = \binom{C_{1}}{C_{1}}\binom{C_{1} + C_{2}}{C_{2}}...\binom{C_{1} + C_{2} + ... + C_{N}}{C_{N}}
```


## Heap

- **by default priority_queue in cpp is MAX-HEAP, in Java it is MIN-HEAP by default**

- min heap creation

  ```cpp
    priority_queue<int, vector<int>, greater<int>> pq;
  ```
