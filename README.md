# Immutable Data Structures Comparison (C, C++, Python, Java)

| **Feature**                      | **C**                              | **C++**                            | **Python**                                  | **Java**                                  |
|-----------------------------------|------------------------------------|------------------------------------|---------------------------------------------|-------------------------------------------|
| **Immutable List (Linked List)**  | Custom implementation, using `const` pointers | Standard `const` pointers and `std::list` | `tuple` (immutable container, not a linked list) | `List` can be immutable with `Collections.unmodifiableList()` |
| **Time Complexity for Insert**    | \( O(1) \) (with linked list)      | \( O(1) \) (using `std::list`)      | \( O(1) \) for `tuple` creation (if fixed size)  | \( O(1) \) for `Collections.unmodifiableList()` |
| **Time Complexity for Access**    | \( O(n) \) (sequential access)     | \( O(n) \) (sequential access)     | \( O(1) \) for indexed access in `tuple`     | \( O(1) \) for indexed access in `List` |
| **Memory Management**             | Manual (via pointers, malloc/free) | Automatic (RAII)                   | Automatic (garbage collected)               | Automatic (garbage collected)             |
| **Side-effect Free Operations**   | Manual handling of memory leaks and modification prevention | Uses `const` for immutability, manual memory management | `tuple` is immutable, no side-effects | `Collections.unmodifiableList()` is immutable |
| **Best Use Case**                 | When you need fine-grained memory control | If you need flexibility with both mutable and immutable objects | Best for when immutability and ease of use is required | Used for protecting a collection from modification |
| **Immutable HashMap**             | Custom implementation with `const` and pointers | `std::map` can be made immutable with custom code | `frozenset`, `dict` (with immutability via `frozenset`) | `Collections.unmodifiableMap()` for immutability |
| **Time Complexity for Lookup**    | \( O(\log n) \) for balanced tree or hashing | \( O(\log n) \) for `std::map` or \( O(1) \) for `unordered_map` | \( O(1) \) average for dictionary access | \( O(1) \) for `unmodifiableMap` with hashing |
| **Mutability Control**            | Manual, use `const` pointers       | Use `const` with `std::map` or `std::list` | `frozenset` or custom classes for immutability | `Collections.unmodifiableMap()` prevents modification |

## Key Points:
- **C**: Requires manual management for memory and immutability using pointers. Custom implementations for immutable lists and maps are necessary.
- **C++**: Uses `const` keyword and standard libraries like `std::list` and `std::map`. You can enforce immutability with custom wrappers or smart pointers.
- **Python**: Native support for immutable collections with `tuple`, `frozenset`, and custom immutable data structures. The language makes it easier to work with immutable structures.
- **Java**: Provides built-in support for immutable collections through `Collections.unmodifiableList()` and `Collections.unmodifiableMap()`.
