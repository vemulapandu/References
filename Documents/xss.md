# XSS

Cross-site scripting. XSS vulnerabilities can lead to the injection of malicious scripts, posing a significant security
risk and potentially compromising the confidentiality and integrity of user data.

---

### CWE Reference: CWE-79

## Patterns

```
import android.webkit.WebView;

public class WebViewExample {
    public static void main(String[] args) {
        // Matched line of code
        String htmlContent = "<html><body><script>alert('Hello');</script></body></html>";
        WebView myWebView = new WebView();
        myWebView.loadData(htmlContent, "text/html", "UTF-8");

        // Additional code for illustration
        // ...
    }
}
```

## Regex

```
WebView\.loadData\(\s*".*<script>.*"\s*,\s*".*"\s*,\s*".*"\s*\);
```

## Owasp-Mobile: M2 Inadequate Supply Chain Security
