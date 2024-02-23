# Unvalidated CORS Origin

---

It refers to the use of Cross-Origin Resource Sharing (CORS) mechanisms without proper validation of the origin.

### CWE Reference: CWE-942

## Patterns

```
// Example: Setting CORS headers without proper validation
response.setHeader("Access-Control-Allow-Origin", request.getHeader("Origin"));
```

## Regex

```
response\.setHeader\("Access-Control-Allow-Origin",\s*request\.getHeader\("Origin"\)\s*\);
```