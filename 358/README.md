## Rust language

My other prefered language...

### Source code

```rust
fn is_prime(n: u64) -> bool {
    if n < 2 {
        return false;
    }
    for i in 2..=((n as f64).sqrt() as u64) {
        if n % i == 0 {
            return false;
        }
    }
    true
}

fn main() {
    let mut primes = Vec::new();
    let mut num = 10001; // Start checking from the first number above 10,000

    // Generate primes above 10,000
    while primes.len() < 100 { // Arbitrarily large limit to ensure we find enough primes
        if is_prime(num) {
            primes.push(num);
        }
        num += 1;
    }

    // Find the first set of five consecutive primes whose average is also prime
    for i in 0..(primes.len() - 4) {
        let sum: u64 = primes[i] + primes[i + 1] + primes[i + 2] + primes[i + 3] + primes[i + 4];
        let average = sum / 5;

        if sum % 5 == 0 { // Check if the sum is divisible by 5 to ensure average is an integer
            if is_prime(average) {
                println!(
                    "The first set of five consecutive primes above 10,000 whose average is also prime: {:?}",
                    &primes[i..i + 5]
                );
                println!("Average: {}", average);
                break;
            }
        }
    }
}
```

### Output

```text
The first set of five consecutive primes above 10,000 whose average is also prime: [10079, 10091, 10093, 10099, 10103]
Average: 10093
```

