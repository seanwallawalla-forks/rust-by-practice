<div align="center">
    <img height="150" src="https://github.com/sunface/rust-by-practice/blob/master/en/assets/logo.png">
</div>

<p align="center">
    <span>English</span>
    <span> | </span>
    <a href="https://github.com/sunface/rust-by-practice/blob/master/zh-CN/src/why-exercise.md">中文</a>
</p>
    
<p align="center">Practice Rust with challenging examples, exercises and projects</p>
    
<div align="center">

[![Stars Count](https://img.shields.io/github/stars/sunface/rust-by-practice?style=flat)](https://github.com/sunface/rust-by-practice/stargazers) [![Forks Count](https://img.shields.io/github/forks/sunface/rust-by-practice.svg?style=flat)](https://github.com/naaive/orange/network/members)
[![LICENSE](https://img.shields.io/badge/license-mit-green?style=flat)](https://github.com/sunface/rust-by-practice/blob/master/LICENSE)
</div>

This book was designed for easily diving into and get skilled with Rust, and it's very easy to use: All you need to do is to make each exercise compile without ERRORS and Panics !


## Reading online

- [https://practice.rs](https://practice.rs)

## Running locally

We use [mdbook](https://rust-lang.github.io/mdBook/) building our exercises. You can run locally with below steps:

- Clone the repo
```shell
$ git clone git@github.com:sunface/rust-by-practice.git
```
- Install mdbook using Cargo
```shell
$ cargo install mdbook
```

- For Book in English
```shell
$ cd rust-by-practice && mdbook serve en/
```

- For Book in Chinese
```shell
$ cd rust-by-practice && mdbook serve zh-CN/
```

## Features

Part of our examples and exercises are borrowed from [Rust By Example](https://github.com/rust-lang/rust-by-example), thanks for your great works!

Although they are so awesome, we have our own secret weapons :)

- There are three parts in each chapter: examples, exercises and practices

- Besides examples, we have `a lot of exercises`, you can Read, Edit and Run them ONLINE

- Covering nearly all aspects of Rust, such as async/await, threads, sync primitives, optimizing, standard libraries, tool chain, data structures and algorithms etc.

- Every exercise has its own solutions

- The overall difficulties are a bit higher and from easy to super hard: easy 🌟 medium 🌟🌟 hard 🌟🌟🌟 super hard 🌟🌟🌟🌟

**What we want to do is fill in the gap between learning and getting started with real projects.**

## Some of our exercises

🌟🌟🌟 Tuple struct looks similar to tuples, it has added meaning the struct name provides but has no named fields. It's useful when you want give the whole tuple a name, but don't care the fields's names.

```rust

// fix the error and fill the blanks
struct Color(i32, i32, i32);
struct Point(i32, i32, i32);
fn main() {
    let v = Point(___, ___, ___);
    check_color(v);
}

fn check_color(p: Color) {
    let (x, _, _) = p;
    assert_eq!(x, 0);
    assert_eq!(p.1, 127);
    assert_eq!(___, 255);
 }
```

🌟🌟 Within the destructuring of a single variable, both by-move and by-reference pattern bindings can be used at the same time. Doing this will result in a partial move of the variable, which means that parts of the variable will be moved while other parts stay. In such a case, the parent variable cannot be used afterwards as a whole, however the parts that are only referenced (and not moved) can still be used.
```rust

// fix errors to make it work
#[derive(Debug)]
struct File {
    name: String,
    data: String,
}
fn main() {
    let f = File {
        name: String::from("readme.md"),
        data: "Rust By Practice".to_string()
    };

    let _name = f.name;

    // ONLY modify this line
    println!("{}, {}, {:?}",f.name, f.data, f);
}
```

🌟🌟 A match guard is an additional if condition specified after the pattern in a match arm that must also match, along with the pattern matching, for that arm to be chosen.
```rust,editable

// fill in the blank to make the code work, `split` MUST be used
fn main() {
    let num = Some(4);
    let split = 5;
    match num {
        Some(x) __ => assert!(x < split),
        Some(x) => assert!(x >= split),
        None => (),
    }
}
```
