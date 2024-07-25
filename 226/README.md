# funmath226

## Problem statement

[URL link](https://www.linkedin.com/feed/update/urn:li:activity:7206485712089600000?utm_source=share&utm_medium=member_desktop)

```text
Fun Math #226

A Pythagorean triplet is a set of three natural numbers, a<b<c, for which a^2+b^2=c^2.

What is the only one Phytagorean triplet for which a+b+c=200?
```
Revisiting Pythagorean triple but using **List comprehension** or to be more precise _emulation_ of the construct by means of Macro with Rust language.

## Source code

```rust
use list_comprehension::comp;

fn pythagorean(n: u32) -> Vec<(u32, u32, u32)> {
    let triplets: Vec<(u32, u32, u32)> = comp![
        (x, y, z)
        
        , x in 1..=n
        , y in x..=n
        , z in y..=n
        
        , (x as u32).pow(2) + (y as u32).pow(2) == (z as u32).pow(2)
        , (x + y + z) == n
    ];
    
    triplets
}

fn main() {
    for triplet in pythagorean(200) {
        println!("\n{:?}", triplet);
    }
}
```

I appreciate the conciseness and readability of the code like so ❤️ 

## Output

```text
(40, 75, 85)
```

## References

  - [Rust Programming Language](https://www.rust-lang.org/)
  - [List comprehension Crate](https://crates.io/crates/list_comprehension)
  - [Fun Math 226 Problem statement](https://www.linkedin.com/feed/update/urn:li:activity:7206485712089600000?utm_source=share&utm_medium=member_desktop)
  - [List comprehension Wikipedia entry](https://en.wikipedia.org/wiki/List_comprehension)
  - [Pythagorean triple Wikipedia entry](https://en.wikipedia.org/wiki/Pythagorean_triple)
