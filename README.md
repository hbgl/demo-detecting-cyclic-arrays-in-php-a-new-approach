# Detecting cyclic arrays in PHP

This repository contains the code snippets from the accompanying blog post: https://hbgl.dev/detecting-cyclic-arrays-in-php-a-new-approach/

The file [functions.php](https://github.com/hbgl/demo-detecting-cyclic-arrays-in-php-a-new-approach/blob/main/functions.php) contains are a couple of functions that can detect cyclic arrays to various degrees of success. If you are just looking for a good working implementation, use [is_cyclic_count](https://github.com/hbgl/demo-detecting-cyclic-arrays-in-php-a-new-approach/blob/main/functions.php#L3).

## Running tests

```
composer run test
```

Please note that the test case _Is cyclic marker with data set "Bomb"_ is intended to fail. I left it in there to illustrate that the particular function does not work correctly.

## Running benchmarks

```
composer run bench
```

The benchmarks paint a clear picture. The winner is the `count` variant, especially when it comes to larger arrays. I also benchmarked the `marker` variant for illustration purposes, even though the implementation is fundamentally broken ([see why](https://hbgl.dev/why-it-is-impossible-to-detect-cyclic-arrays-in-pure-php/)). Benchmarks were only run on a subset of arrays that can be successfully checked by all implementations.
