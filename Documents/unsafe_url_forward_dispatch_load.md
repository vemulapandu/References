# Unsafe URL Forward Dispatch Load

Unsafe URL forward, dispatch, or load from remote source. It indicates a potential security risk.

---

### CWE Reference: CWE-601

## Patterns

```
const input = 'loadUrl("https://example.com");';
```

## Regex

```
loadUrl\((?:"|\')(.*?)(?:"|\')\);
```

## Owasp-Mobile: M5 Insecure Communication
