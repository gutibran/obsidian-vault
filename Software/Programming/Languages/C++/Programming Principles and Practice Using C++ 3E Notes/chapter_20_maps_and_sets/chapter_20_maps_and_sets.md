# Associative container overview
- `map` is an ordered sequence of key-value pairs where you can look up a value based on a key.
- `unordered_map` is optimized for keys that are strings.
- `map` and `unordered_map` are also known as **associative arrays**, **hash tables**, and **red-black trees**. C++ generally refers to these as **associative containers**.
## The type in the standard library
- `map` for ordered key-value pairs
- `set` for ordered keys
- `unordered_map` for unordered key-value pairs
- `multimap` is the same as `map` except that it contain a key multiple times
- `multiset` is the same as `set` except that it can contain a key multiple times
- `unordered_multimap`is the same as `unordered_map` except that it can contain a key multiple times
- `unordered_multiset` is the same as `unordered_set` except that it can contain a key multiple times
# `map`
## Example usage
```c++
#
// declare a map
```