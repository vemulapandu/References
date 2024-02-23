# Sensitive Android File Leak

Leaking sensitive Android file. Leaking sensitive information, especially to external storage or other unauthorized
locations, poses a serious security risk and can have severe consequences.

---

### CWE Reference: CWE-200

## Patterns

```
import java.io.FileOutputStream;
import java.io.IOException;

public class FileOutputStreamExample {
    public static void main(String[] args) {
        try {
            // Matched line of code
            FileOutputStream fos = new FileOutputStream("/sdcard/example.txt");

            // Additional code for illustration
            fos.write("Hello, World!".getBytes());
            fos.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## Regex

```
FileOutputStream\s+\w+\s+=\s+new\s+FileOutputStream\s*\(\s*"[^"]*\/sdcard\/[^"]*"\s*\);
```