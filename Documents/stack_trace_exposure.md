# Stack Trace Exposure

Information exposure through a stack trace. Exposing stack traces can be a security risk, especially if sensitive
details are revealed.

---

### CWE Reference: CWE-209

## Patterns

```
import android.util.Log;

public class LogExample {
    public static void main(String[] args) {
        // Matched line of code
        try {
            // Some code that may throw an exception
            throw new Exception("Example exception");
        } catch (Exception e) {
            Log.e("TAG", "Error occurred:", e);
        }

        // Additional code for illustration
        // ...
    }
}
```

## Regex

```
Log\.(v|d|i|w|e|wtf)\([^;]+e\.printStackTrace\(\);
```