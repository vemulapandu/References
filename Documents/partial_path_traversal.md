# Partial Path Traversal

Partial path traversal vulnerability. Partial path traversal vulnerabilities can pose security risks by potentially
allowing unauthorized access to files outside of the intended directory.

---

### CWE Reference: CWE-22

## Patterns

```
import java.io.File;

public class FileTraversalExample {
    public static void main(String[] args) {
        // Matched lines of code
        File file1 = new File("/path/to/some/file");
        File file2 = new File("/path/to/parent/directory/..");

        // Additional code for illustration
        // ...
    }
}
```

## Regex

```
(File|new\s+File)\(.*[\"']\.\.[\"'].*\)
```

## Owasp-Mobile: M4: Insufficient Input/Output Validation
