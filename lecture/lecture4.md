# Initialization and References
## Uniform initialization: 
+ curly bracket (花括号`{}`) initialization. 
+ available for all types, immediate initialization on declaration
+ `std::vector<int> vec{1,3,5}; // makes {1, 3, 5}`
+ `int x{5};`
+ comparison: `std::vector<int> vec1(3,5); // makes {5, 5, 5}`

## Structured Binding using auto:
+ `auto [a, b] = p; // pair<int,int>`
+ no nested structured binding

## Reference
+ an alias (another name) for a named variable
+ rvalue can't be referenced

```cpp
void shift(vector<std::pair<int, int>>& nums) {
    for (auto& [num1, num2]: nums) {
        num1++;
        num2++;
    }
}
shift({{1, 1}}); // error: rvalue
// correct way
// auto my_nums = {{1, 1}};
// shift(my_nums);
```

### Definition: l-values vs r-values
1. l-values
    + l-values can appear on the left or right of an =
    + l-values have names 
    + l-values are not temporary

2. r-values
    + r-values can ONLY appear on the right of an =
    + r-values don’t have names 
    + r-values are temporary

### Const and Const References
+ const indicates a variable can’t be modified
+ can’t declare non-const reference to const variable