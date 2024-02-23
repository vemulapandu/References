# Unsafe Double Checked Locking

Double-checked locking is not thread-safe. This can lead to race conditions and incorrect behavior in a multithreaded
environment.

---

### CWE-Reference: CWE-609

## Patterns

```
public class DoubleCheckedLockingExample {
    private static Object myObject;

    // Matched code snippet
    public static void initializeMyObject() {
        if (myObject == null) {
            synchronized (DoubleCheckedLockingExample.class) {
                if (myObject == null) {
                    myObject = new Object();
                }
            }
        }
    }

    // Additional code for illustration
    // ...
}
```

## Regex

```
\s*if\s*\(\s*\w+\s*==\s*null\s*\)\s*{\s*[\n\s]*\bsynchronized\s*\(\s*\w+\.\w+\(\)\s*\)\s*{\s*[\n\s]*if\s*\(\s*\w+\s*==\s*null\s*\)\s*{\s*\w+\s*=\s*new\s*\w+\(\);\s*}\s*}\s*}
```