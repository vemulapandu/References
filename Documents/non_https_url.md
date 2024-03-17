# Non Https URL

Failure to use HTTPS URLs. While it may not lead to an immediate security breach, it represents a potential security
risk. Addressing warnings related to the use of non-HTTPS URLs is important for ensuring secure communication,
especially when handling sensitive information.

---

### CWE Reference: CWE-693

## Patterns

Any Http link

## Regex

```
\\bhttp(?:s)?://[-A-Za-z0-9+&@#/%?=~_|!:,.;]*[-A-Za-z0-9+&@#/%=~_|]
```

## Owasp-Mobile: M5 Insecure Communication
