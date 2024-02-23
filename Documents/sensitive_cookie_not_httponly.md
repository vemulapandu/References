# Sensitive Cookie Not HttpOnly

Sensitive cookies without the HttpOnly response header set. Setting the HttpOnly flag for sensitive cookies is
considered a security best practice to prevent client-side script access.

---

### CWE Reference: CWE-1004

## Patterns

```
function setCookie(cookieString) {
    // Matched line of code
    document.cookie = cookieString;
}

// Example usage
setCookie("name=value; path=/; domain=example.com"); // Matches
setCookie("name=value; HttpOnly"); // Does not match
```

## Regex

```
setCookie\s*\(\s*".*(?<!HttpOnly)\b.*"\s*\);
```