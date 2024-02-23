# Intent Redirection

Android Intent redirection. Intent redirection vulnerabilities can lead to unintended and potentially harmful behavior,
making them critical to address for the overall security of the application.

---

### CWE-Reference: CWE-926

## Patterns

```
import android.content.Intent;
import android.net.Uri;

public class IntentExample {
    public static void main(String[] args) {
        // Matched line of code
        Intent myIntent = new Intent(Intent.ACTION_VIEW, Uri.parse("https://example.com"));

        // Additional code for illustration
        // ...

    }
}
```

## Regex

```
Intent\s+\w+\s*=\s*new\s+Intent\s*\(\s*[^,]+,\s*Uri\.parse\(\s*"[^"]+"\s*\)\s*\);
```