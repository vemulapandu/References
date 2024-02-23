# Call to Thread Run

In most cases a direct call to a Thread object's run() method is a bug. The programmer intended to begin a new thread of
control, but accidentally called run() instead of start(), so the run() method will execute in the caller's thread of
control.

---

### CWE Reference: CWE-572

## Patterns

```
public class ExampleThread {
    public static void main(String[] args) {
        Thread myThread = new Thread();
        myObject.run();
    }
}
```

## Regex

```
Thread\s*\w+\s*=\s*new\s*Thread\(\)\s*;\s*\w+\.\s*run\s*\(\s*\);
```