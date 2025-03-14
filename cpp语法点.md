

**如果heap内部存的是ListNode\*，需要重定义cmp obj：**
```c++
priority_queue<ListNode*, vector<ListNode*>, cmp>;
```
1. priority_queue需要的cmp是一个struct
2. 函数返回true时，a被放在b后面
```c++
struct cmp {
    bool operator() (ListNode* a, ListNode* b) {
        return a->val > b->val;  // 这样是最小堆，因为更大的a在后，更小的b在前
    }
};
```

**不需要重定义cmp obj的话，直接用greater<T>就好了：**
```c++
priority_queue<int, vector<int>, greater<int>> right;
```

**sort中的cmp是一个函数，不是obj：**
```cpp
sort(vec.begin(), vec.end(), cmp);
```
1. sort需要的cmp是一个bool函数
2. 函数返回true时，a被放在b前面
```cpp
bool cmp(ListNode* a, ListNode* b) {
    return a->val > b->val; // 这样是降序排列，因为更大的a在前
}
```
