## D language

My usual language of choice...

### Source code

```d
import std.stdio;
import std.conv;
import std.algorithm;

void main() {
    const N = 3;
    
    int count = 0;
    
    foreach (n; 10^^(N-1)..10^^N) {
        if (isValid(n)) {
            count++;
        }
    }
    
    writefln("\nTotal valid %d-digits numbers: %d", N, count);
}

bool isValid(int n) {
    return (n.to!string.map!(c => c-'0').sum(0uL)<9+1);
}
```

### Output

```text
Total valid 3-digits numbers: 165
```
