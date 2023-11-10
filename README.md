# cpp-cheatsheet
snippets for cpp competitive programming

## Numeric data type range

code to generate these values

`cout << "short" << " | " << numeric_limits<short>::max() << nl;`

|type|max|
|--|--|
|short | 32767
|unsigned short | 65535
|int | 2147483647
|unsigned int | 4294967295
|long | 9223372036854775807
|long long | 9223372036854775807
|unsigned long long | 18446744073709551615
|unsigned long | 18446744073709551615
|float | 3.40282e+38
|double | 1.79769e+308
|long double | 1.18973e+4932

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

