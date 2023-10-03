# Basic cpp

> Concepts

```c++
// "" -> strings
// '' -> character
```

> Output

```c++
  cout << "hello" << endl;
```

```bash
hello
```

> For-loop

```c++
  for (int i = 0, j = 0; i < 5; i++, ++j)
    cout << i << ' ' << j << ' ' << '\n';
```

```bash
0 0
1 1
2 2
3 3
4 4
```

> While Loop

```c++
  int i = 5;
  while (i > 0){
    cout << i << '\n';
    --i;
  }
```

```bash
5
4
3
2
1
```

> Do-While Loop

```c++
int i = 5;
do
{
  cout << i << '\n';
} while (i != 5);
```

```bash
5
```

# C++ stl library

- Algorithms and containers
- With template classes

# Boiler plate

```c++
#include<bits/stdc++.h>
// #include<iostream>
using namespace std;

int main(){

    // cout << ' ' << endl;
    return 0;
}
```

## Input/Output

```c++
std::cin >> str;   // Read a string
std::cout << str;  // Print a string
```

# Containers

## Vector

```c++
#include <vector>
```

```c++
std::vector<int> vec; // Declares an empty vector of integers
std::vector<int> vec = {1, 2, 3, 4, 5}; // Declares and initializes a vector

vector<int> v2(size);   // {0, 0, 0, 0, 0}
vector<int> vec(size, ele);  /// {ele, ele}
```

```c++
// Initializing 2D vector
auto M = 4;             // num of rows
auto N = 3;             // num of cols in each row
auto default_value = 1; // default value of all int elements
vector<vector<int>> matrix(M, vector<int>(N, default_value));
```

```c++
// Set To Vector
unordered_set<int> set = {1, 4, 2, 3};
vector<int> v(set.begin(), set.end()); // {3, 2, 4, 1}
```

```c++
// push_back: Adds an element to the end of the vector.
vector.push_back(element);
```

```cpp
// pop_back: Removes the last element from the vector.
vector.pop_back();
```

```cpp
// size: Returns the number of elements in the vector.
int size = vector.size();
```

```cpp
// empty: Checks if the vector is empty.
if(vector.empty()) {
    // Vector is empty
}
```

```cpp
// clear: Removes all elements from the vector.
vector.clear();
```

```cpp
// front: Returns a reference to the first element.
element = vector.front();
```

```cpp
// back: Returns a reference to the last element.
element = vector.back();
```

```cpp
// at: Accesses an element with bounds checking.
element = vector.at(index);
```

```cpp
int value = vector[0];
```

```cpp
// update element
vector[0] = 100;
```

```cpp
// begin and end: Return iterators pointing to the first and one past the last element, respectively.
auto it = vector.begin();  // iterator to the beginning
auto end = vector.end();   // iterator to the end
```

```cpp
// insert: Inserts elements at a specified position.
vector.insert(iterator, element);

//{300, 100, 100}
vec.insert(vec.begin() + 1, 2, 10);
//{300, 10, 10, 100, 100}
```

```cpp
// erase: Removes elements from a specified position.
vector.erase(iterator);

// 10 20 12 23 35
v.erase(v.begin() + 2, v.begin() + 4); //{10, 20, 35}[start, end)
```

```cpp
// swap: Swaps the contents of two vectors.
vector1.swap(vector2);
```

```cpp
// sort: Sorts the elements in the vector.
sort(vector.begin(), vector.end());
```

```cpp
// reverse: Reverses the order of elements in the vector.
reverse(vector.begin(), vector.end());
```

```c++
// If size of vec is given:
    vector<int> V(size);
    for (int i = 0; i < size; i++){
        cin >> V[i]; // or read through a variable and use push_back()
    }

// If size of vec not given:
    int input;
    while (cin >> input)
        V.push_back(input);
```

```c++
for (int i = 0; i < v5.size(); ++i)
  cout << v5[i] << ' ';

for (int& ele : vector)
  cout << ele << " "; // 1 2 3

for (vector<int> row : vector2D)
  for (int ele : row)
    cout << ele << " ";

copy(v.begin(), v.end(), ostream_iterator<int>(cout, " "));

for (vector<int>::iterator it = v5.begin(); it != v5.end(); ++it) // use auto keyword
  cout << *it <<" ";

for (auto it = v5.rbegin(); it != v5.rend(); ++it) // print vector in reverse
  cout << *it << " ";
```

## String

```c++
#include <string>
```

```c++
string str = "mango";
```

```c++
char first_char = str[0];   // Access first character
char last_char = str.back(); // Access last character
char first_char = str.front(); // Access front character
```

```c++
int length = str.size(); // or str.length(); 5
```

```c++
cout << str.empty( ) << endl; //yes 1 no 0
```

```c++
str.push_back('c') ;
cout << str << endl; //mangoc
```

```c++
//mangoc
str.pop_back() ;
cout << str << endl; //mango
```

```c++
//mango
str.append ("apple");
cout << str << endl; //mangoapple

//mangoapple
str.append (2, 'x') ;
cout << str << endl; //mangoapplexx
```

```c++
string substring = str.substr(start_pos, length);
```

```c++
for (char& ch: str)
    cout << ch <<' '; // m a n g o a p p l e x x
```

```c++
for (int i = 0; i < str.length(); i++)
    cout << str[i] << ' ';
// m a n g o a p p l e x x
```

```c++
// mango
swap(str[0], str[str.size() - 1]);
cout << str << endl;
// oangm
```

## Map Behaviour

> Declaraing key creats the pair
>
> > map.count()
> > // returns number of elements with specified key: makes sense for multimap
> > // otherwise if key present 1 else 0

```c++
  map<int, char> mp = {{1, 'a'}, {77, 'z'}};

    cout << mp.count(9);
    cout << mp[9]; //this cause a pair to be created {9, _}
    cout << mp.count(9);
```

```bash
01
```

```c++
  map<int, char> mp = {{1, 'a'}, {77, 'z'}};

  auto it = mp.find(9);
  if (it != mp.end())
      cout << it->second; // Access value associated with key 9
  else
      cout << "Key 9 not found in the map" << endl;

  cout << mp[9];

  if (mp.find(9) != mp.end())
      cout << "Found uuuu"; //we can't print the value as it is initialized as null
  else
      cout << "Key 9 not found in the map";
```

```bash
Key 9 not found in the map
Found uuuu
```

## Map

> Sorted and unique

```c++
#include <map>
```

```c++
  map<int, char> myMap; // Creates an empty map
  // eg: { { 1, 'a' }, { 2, 'b' } }

  map<int, char> mp = {{1, 'a'}, {77, 'z'}};
```

> Access Value:

```c++
char ch1 = mp.at(1);  // 'a'
char ch2 = mp[77];    // 'z'
```

> Insert value

```c++
myMap.insert(make_pair(key, value)); // Inserts a key-value pair into the map

myMap[key] = value; // Inserts a key-value pair into the map
```

```c++
if (myMap.empty()) {
    // Map is empty
}
```

```c++
int mapSize = myMap.size(); // Get the number of key-value pairs in the map
```

> Check if Key Exists:

```c++
if (myMap.find(key) != myMap.end()) {
    // Key exists in the map
}
```

```c++
auto it = mp.find(key); // Finds the first occurrence of the key

if (it != mp.end())
  ValueType value = it->second; // Retrieves the value associated with the key
else
    // Key not found
```

> Erase Key-Value Pair:

```c++
myMap.erase(key); // Removes the key-value pair with the specified key
```

```c++
for (const auto& pair : myMap) {
  std::cout << pair.first << " : " << pair.second << std::endl;
}
```

```c++
for (auto it = myMap.begin(); it != myMap.end(); ++it) {
    KeyType key = it->first;
    ValueType value = it->second;
    // Do something with key and value
}
```

### Multi Map

> Sorted and Not unique

```c++
#include <map>
```

```c++
std::multimap<KeyType, ValueType> myMultimap; // Creates an empty multimap
```

```c++
  multimap<int, char> mp = {{1, 'a'}, {77, 'z'}, {1, 'a'}};

  cout << mp.count(1) << endl; // 2
```

### unordered_map

> Unsorted and unique

```c++
#include <unordered_map>
```

```c++
  unordered_map<int, char> unmap; // Creates an empty unordered map
```

### Multi unordered_map

```c++

```

## Set

> - s[0] is invalid (set has no reference operator [])
>   Sorted and unique

```c++
#include <set>
```

```c++
  set<int> mySet; // Creates an empty set of 'int'

  set<int> mySet = {3, 21, 1};
```

```bash
# output when printed
{1, 3, 21}
```

```c++
  mySet.insert(element); // Inserts an element into the set
```

```c++
if (mySet.empty()) {
  // Set is empty
}
```

```c++
int setSize = mySet.size(); // Get the number of elements in the set
```

```c++
mySet.erase(element); // Removes the specified element from the set
```

> Check if Element Exists:

```c++
  if (mySet.count(element) > 0) {
    // Element exists in the set
  }
```

```c++
auto it = mySet.find(element);

if (it != mySet.end()) {
    // Element found
    // Use *it to access the element
    cout << *it;
}
```

> Iterate Over Set

```c++
  for (const auto& element : mySet) {
    // Do something with element
    std::cout << element << " ";
  }
```

### Multi set

> Sorted and Not unique

```c++
#include <set>
```

```c++
multiset<int> myMultiset; // Creates an empty multiset

multiset<int> myMultiset = {1, 1, 21, 2};
```

```bash
# output when printed
1 1 2 21
```

```c++
cout << myMultiset.count(1); // 2
```

```c++
// {1, 1, 2, 3}
myMultiset.erase(element); // Removes all occurrences of the specified element from the multiset
// {2, 3} eg: if element = 1
```

### unordered_set

> Not Sorted and unique

```c++
#include <unordered_set>
```

```c++
std::unordered_set<int> myUnorderedSet; // Creates an empty unordered set
```

### Multi unordered_set

```c++

```

## Stack: LIFO

> - We cannot initialize: stack st(1,2,3) | stack st = {1,2,3};
> - using st.top() or st.pop() when stack is empty 'll generate error
> - Access by st[1] is invalid
> - Stack does not have an iterator
> - pop(): pops the top
> - All op: O(1)

```c++
#include<stack>
```

```c++
// Creates an empty stack of integers
stack<int> myStack;
  myStack.push(1);   // {1}
  myStack.push(2);   // {1, 2}
  myStack.push(3);   // {1, 2, 3}
  myStack.push(4);   // {1, 2, 3, 4}
  myStack.push(5);   // {1, 2, 3, 4, 5}
```

```c++
// {1, 2, 3, 4, 5}
myStack.top() += 1000;   // top => 5

// {1, 2, 3, 4, 1005}
int topElement = myStack.top()  // 1005
```

```c++
// {1, 2, 3, 4, 1005}
myStack.pop();
// {1, 2, 3, 4}
```

```c++
int stackSize = myStack.size(); // 4
```

```c++
cout << myStack.empty(); // yes: 1 no: 0
```

```c++
// The actual stack gets affected
while (!myStack.empty()){
  cout << myStack.top() << ' ';
  myStack.pop();
}
```

```c++
void showstk(stack<int> st){
    // here a copy of stack is passed not the orginal stack
    // so removing ele does not actually affect org stack
    while (!st.empty()) {
      cout << st.top() << ' ';
      st.pop();
    }
    std::cout << std::endl;
}
```

## Queue:FIFO

> - We cannot initialize: queue q(1,2,3) | queue q = {1,2,3};
> - q.back(), q.front() or q.pop() when queue is empty 'll generate error
> - Access by q[1] is invalid
> - Queue does not have an iterator
> - pop(): pops the front
> - All op : O(1)

```c++
#include<queue>
```

```c++
// Creates an empty queue of integers
queue<int> myQueue;
  myQueue.push(1);    // {1}
  myQueue.push(2);    // {1, 2}
  myQueue.push(3);    // {1, 2, 3}
```

```c++
// {1, 2, 3}
myQueue.back() += 5;

// {1, 2, 8}
int backElement = myQueue.back(); // prints 8
```

```c++
myQueue.front() += 5;

int frontElement = myQueue.front(); // prints 6
// {6, 2, 8}
```

```c++
// {6, 2, 8}
myQueue.pop();
// {2, 8}
```

```c++
int queueSize = myQueue.size(); // 2
```

```c++
// yes: 1 no: 0
if (myQueue.empty()) {
  // Queue is empty
}
```

```c++
// The actual queue gets affected
while (!myQueue.empty()) {
  cout << myQueue.front() << " "; // Print the front element
  myQueue.pop(); // Dequeue the front element
}
std::cout << std::endl;
```

```c++
void showq(queue<int> g){
    // here a copy of queue is passed not the orginal queue
    // so removing ele does not actually affect org queue
    while (!g.empty()) {
      cout << g.front() << ' ';
      g.pop();
    }
}
```

## Priority Queue

> - Same pointers of queue apply here

```c++
#include <queue>
```

### Max Heap

```c++
  // Creates an empty max priority queue
  std::priority_queue<int> maxpq;
```

```c++
  maxpq.push(5); // Enqueues the value 5 into the priority queue
```

```c++
  maxpq.pop(); // Dequeues the maximum element from the priority queue
```

```c++
  int maxValue = maxpq.top(); // Retrieves the maximum element (root) without removing it
```

```c++
  if (maxpq.empty()) {
    // Priority queue is empty
  }
```

```c++
  int queueSize = maxpq.size(); // Get the size of the priority queue
```

> This loop will print the elements in the priority queue from highest to lowest.

```c++
// The original maxpq is not affected
  std::priority_queue<int> tempQueue = maxpq; // Create a copy to preserve original data

  while (!tempQueue.empty()) {
      std::cout << tempQueue.top() << " "; // Print the maximum element
      tempQueue.pop(); // Dequeue the maximum element
  }
  std::cout << std::endl;
```

### Min Heap

```c++
// smallest element has the highest priority
priority_queue<int, vector<int>, greater<int>> minipq;
```

```c++
// Define a custom comparison function for min heap
struct CompareMin {
  bool operator()(int a, int b) {
    return a > b; // Returns true if a should go before b (min heap condition)
  }
};

std::priority_queue<int, std::vector<int>, CompareMin> myMinPriorityQueue; // Creates an empty min priority queue
```

## Pair

```c++
// Pair initializing
  pair<int, int> p1 = {1, 2};
  cout << p1.first << " " << p1.second << endl;
```

```c++
// Pair constructing function
pair<string, int> p4;
p4 = make_pair("one one one",122);
cout << p4.first << " " << p4.second << endl;
```

```c++
// nested pairs
pair<int, pair<int, string>> p4 = {3, {4, "helo"}};
cout << p4.first << endl; // 3
cout << p4.second.first << ' ' << p4.second.second << endl; // 4 helo
```

```c++
// Array of Pairs
pair<int, int> arr[] = {{1, 2}, {3, 4}, {5, 6}};
cout << arr[2].second << endl; // 6
```

```c++
// VECTOR OF PAIRS
vector <pair<int, int>> vec = {{1,2},{3,4}};
vec.push_back({1, 2});
vec.emplace_back(1,2); //auto detects data is pair
```

```c++
// Pair Destructing
std::pair<int, char> myPair(5, 'a');
int a;
char b;

std::tie(a, b) = myPair;  // a = 5, b = 'a'
```

```c++
// Alternatively, in C++17 and later:
auto [a, b] = myPair; // a = 5, b = 'a'
```

## Arrays

```c++
int arr[5]; // Declares an array of size 5
int arr[5] = {1, 2, 3, 4, 5}; // Declares and initializes an array
```

```c++
int arr[5] = {0}; // Initializes all elements to 0
```

```c++
// Access element
int element = arr[index]; // Accesses element at index
```

```c++
// Setting Elements:
arr[index] = value; // Sets the value of element at index
```

```c++
int size = sizeof(arr) / sizeof(arr[0]); // Calculates the size of the array
```

```c++
for (int i = 0; i < size; ++i) {
    // Do something with arr[i]
}
```

```c++
// Or, in C++11 and later:
for (int element : arr) {
    // Do something with element
}
```

```c++
std::sort(arr, arr + size); // Requires #include <algorithm>
```

```c++
// Searching in arrays
auto it = std::find(arr, arr + size, value); // Requires #include <algorithm>
if (it != arr + size) {
    // Value found in the array
}
```

```c++
    std::iota(arr, arr + 6, 1); // Fills the array with sequential values
    // {1, 2, 3, 4, 5, 6}
```

## Multi dimensional arrays

```c++
int matrix[3][3]; // Declares a 3x3 matrix
matrix[0][0] = 1; // Accesses & Setting elements of the matrix
```

## Pointer

```c++
    int x = 7;

    cout << x << endl;  // 7
    cout << &x << endl; //0x7bfe1c

    int* ptr = &x;
    cout << *ptr << endl;  //7
    cout << ptr << endl;   //0x7bfe1c
    cout << &ptr << endl;  //0x7bfe10
```

```c++
    int x = 7;
    int* ptr = &x;

    *ptr = 89;

    cout << *ptr << endl;  //89
    cout << x << endl;     // 89
```

## Reference

```c++
    int x = 7;

    cout << x << endl;  // 7
    cout << &x << endl; //0x7bfe14

    int& ref = x;
    cout << ref << endl;  //7
    cout << &ref << endl;  //0x7bfe14
```

```c++
    int x = 7;
    int& ref = x;

    ref = 8;

    cout << ref << endl;  //8
    cout << x << endl;  //8
```

# Algorithm

```c++
#include <algorithm>
```

```c++
vector<int> v = {1, 2, 34};
// lowerbound -> >=
// upperbound  -> >
cout << lower_bound(v.begin(), v.end(), 3) - v.begin() << endl;   // index: 2
cout << lower_bound(v.begin(), v.end(), 2) - v.begin() << endl;   // index: 1
cout << lower_bound(v.begin(), v.end(), 100) - v.begin() << endl; // index: 3(Out of bound)

cout << *lower_bound(v.begin(), v.end(), 34) << endl;             // element: 34
cout << *lower_bound(v.begin(), v.end(), 100);                    // element: 0(Out of bound)
```

# Inbuilt Functions

```c++

```
