# funmath241

## Problem statement

[URL link](https://www.linkedin.com/feed/update/urn:li:activity:7214455399565938688)

```text
Fun Math #241

Shown below are all quadruples {a,b,c,d} where a<b<c<d<1000 and a, b, c, and d are all primes, such that a+1, b+1, c+1, and d+1 form a geometric sequence.

#funmath
```

<p><img src="https://github.com/my-LinkedIn/funmath241/blob/main/funmath241.jpeg"><p>

## Source code

```d
import std.stdio;
import std.array;


// List of first 168 prime numbers under 1000
immutable int[] primes = [
    2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 
    73, 79, 83, 89, 97, 101, 103, 107, 109, 113, 127, 131, 137, 139, 149, 151, 
    157, 163, 167, 173, 179, 181, 191, 193, 197, 199, 211, 223, 227, 229, 233, 
    239, 241, 251, 257, 263, 269, 271, 277, 281, 283, 293, 307, 311, 313, 317, 
    331, 337, 347, 349, 353, 359, 367, 373, 379, 383, 389, 397, 401, 409, 419, 
    421, 431, 433, 439, 443, 449, 457, 461, 463, 467, 479, 487, 491, 499, 503, 
    509, 521, 523, 541, 547, 557, 563, 569, 571, 577, 587, 593, 599, 601, 607, 
    613, 617, 619, 631, 641, 643, 647, 653, 659, 661, 673, 677, 683, 691, 701, 
    709, 719, 727, 733, 739, 743, 751, 757, 761, 769, 773, 787, 797, 809, 811, 
    821, 823, 827, 829, 839, 853, 857, 859, 863, 877, 881, 883, 887, 907, 911, 
    919, 929, 937, 941, 947, 953, 967, 971, 977, 983, 991, 997
];

// Function to check if four numbers are in geometric progression using integer arithmetic
bool isGeometricProgression(int a, int b, int c, int d, int step = 1) {
    return (b + step) * (b + step) == (a + step) * (c + step) && (c + step) * (c + step) == (b + step) * (d + step);
}

void main() {
    writefln("\nFun Math #%s\n", "241");
    
    int count = 0;
    
    foreach (a; primes) {
        foreach (b; primes) {
            if (b <= a) continue;
            foreach (c; primes) {
                if (c <= b) continue;
                foreach (d; primes) {
                    if (d <= c) continue;
                    if (isGeometricProgression(a, b, c, d)) {
                        writefln("Found geometric progression: [%-(%4s, %)]", [a, b, c, d]);
                        count++;
                    }
                }
            }
        }
    }
    
    (count != 0) ? writeln("\nTotal solutions found: ", count) : writeln("\nNo solution found!");
}

```

## Output

```text
Fun Math #241

Found geometric progression: [   2,    5,   11,   23]
Found geometric progression: [   2,   11,   47,  191]
Found geometric progression: [   2,   17,  107,  647]
Found geometric progression: [   5,   11,   23,   47]
Found geometric progression: [  29,   89,  269,  809]
Found geometric progression: [  31,   47,   71,  107]
Found geometric progression: [  31,   79,  199,  499]
Found geometric progression: [  89,  179,  359,  719]
Found geometric progression: [ 499,  599,  719,  863]
```

## Reference

  - [D](https://dlang.org/)
