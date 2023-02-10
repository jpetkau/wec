# wec

Rust crate that defines macros to enable ES-like "spread" syntax for
literal sequences.

```rust
    let arr = [4, 5, 6];

    // `vek!` is a drop-in replacement for `std::vec!`, except you can
    // use `...x` to expand iterables.
    assert_eq!(
        vek![1, 2, 3, ...arr, 7, 8, 9],
        [1, 2, 3, 4, 5, 6, 7, 8, 9]);

    assert_eq!(
        wec![1, 2, 3, ...arr, 7, 8, 9],
        [1, 2, 3, 4, 5, 6, 7, 8, 9]);

    // `iter!` provides the same syntax as iterator, similar to
    // itertools::chain()
    # use std::collections::VecDeque;
    let d: VecDeque<_> = iter![1, 2, 3, ...arr, 7, 8, 9].collect();
```
