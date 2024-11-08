# cpp-cheatsheet
snippets for cpp competitive programming

[link to repo](https://github.com/ashish1729/cpp-cheatsheet)

## Heap

- **VERY IMPORTANT** that element on top of priority queue is the one which is last in the ordering defined 
- **by default priority_queue in cpp is MAX-HEAP, this is important because in Java it is MIN-HEAP by default**

- simple min-heap can be created using following code, but next points mention various other ways for custom comparator

  ```cpp
    priority_queue<int, vector<int>, greater<int>> pq;
  ```

- to create a min heap you have to pass a custom comparing logic, below are some ways to pass custom comparator
  - in the following code I have used some typedefs
    ```cpp
    typedef pair<int, int> ii;
    typedef vector<ii> vii;
    ```
  - I don't understand all of them because I don't know types in CPP properly right now ( like class, pointer, function pointer etc.), so just copy paste for now :P

1. using a class or struct

  ```cpp
  struct compStruct
  {
      bool operator()(ii &a, ii &b)
      {
          return a.first > b.first;
      }
  };
  
  int main() {
      priority_queue<ii, vii, compStruct> pqName;
  }
  ```
  
  
  ```cpp
  class compClass {
  public:
      bool operator() (ii &a, ii&b) {
          return a.first > b.first;
      }
  };
  
  int main() {
        priority_queue<ii, vii, compClass> pqName;
  }
  ```
2. by defining a function ( type is pointer in this case )


  ```cpp
    bool cmp(ii a, ii b) {
        return a.first > b.first;
    }
    
    int main() {
      priority_queue<ii, vii, decltype(cmp)*> pqName(cmp);
    }
  ```

  ```cpp
    bool cmp(ii a, ii b) {
        return a.first > b.first;
    }
    
    int main() {
        priority_queue<ii, vii, function<bool(ii,ii)>> pqName(cmp);
    }
  ```
3. by defining a lambda function ( note that it is not a pointer in this case )

  ```cpp
  
      auto compareFun = [](ii a, ii b ) { return a.first > b.first;};
      priority_queue<ii, vii, decltype(compareFun)> pqName(compareFun);
  ```

  ```cpp
      auto compareFun = [](ii a, ii b ) { return a.first > b.first;};
      priority_queue<ii, vii, function<bool(ii,ii)>> pqName(compareFun);
  ```
4. extending the class with operator overloading
  - I don't know how to overload yet, so I will not write a snippet here, but here is one [youtube video explaining the same](https://www.youtube.com/watch?v=mQZshO2DY4Q)

## alternative operators

|Primary|Alternative|
|-|-|
|  &&	| and	|
|  &=	| and_eq	|
|  &	| bitand	|
|  \|	| bitor	|
|  ~	| compl	|
|  !	| not	|
|  !=	| not_eq	|
|  \|\|	| or	|
|  \|=	| or_eq	|
|  ^	| xor	|
|  ^=	| xor_eq	|
|  {	| <%	|
|  }	| %>	|
|  [	| <:	|
|  ]	| :>	|
|  #	| %:	|
|  ##	| %:%:	|



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

some other equations at [codeforce blog](https://codeforces.com/blog/entry/94470)
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

