# cpp-cheatsheet
snippets for cpp competitive programming

## Binary
``` cpp
a + ~a = -1; // it sets all 1s
-a = 1 + ~a; // can be easily derived using a + -a = 1 + -1 . and replace -1 from previous

(a|b) + (a&b) = a + b;
a^b = (a - (a&b)) + (b - (a&b));  // bits of a which are not in b + bits of b which are not in a
a^b = a + b - 2 * (a&b); // simplifying last line
a^b = (a|b) - (a&b);     // using value of a + b from above , easy to see in venn diagram also , because xor is symmetric difference
```


## STL

### Vectors

```cpp
vector<int> count(26,0)
```

### Set
```cpp

set<int> s;

set.insert(2);
set.erase(2);
set.clear();
set.find(2) != set.end() // checks existence
```

