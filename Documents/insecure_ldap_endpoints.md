# Insecure Ldap Endpoints

Insecure LDAPS Endpoint Configuration. Using insecure LDAPS can lead to the transmission of sensitive information over
unencrypted connections, posing a significant security risk.

---

### CWE Reference: CWE-297

## Patterns

```
String ldapUrl = "ldap://example.com:389";
LdapContext context = new InitialLdapContext(env, null);
```

```
String ldapUrl = "ldap://example.com:389";
Hashtable<String, String> env = new Hashtable<>();
env.put(Context.PROVIDER_URL, ldapUrl);
LdapContext context = new InitialLdapContext(env, null);
```

```
String ldapUrl = "ldap://example.com:389";
Hashtable<String, String> env = new Hashtable<>();
env.put(Context.PROVIDER_URL, ldapUrl);
```

## Regex

```
\bLdapContext\s+[a-zA-Z_][a-zA-Z0-9_]*\s*=\s*new\s*InitialLdapContext\(\s*[a-zA-Z_][a-zA-Z0-9_]*,\s*null\s*\);
```

```
\bHashtable\s*<\s*String,\s*String\s*>\s*[a-zA-Z_][a-zA-Z0-9_]*\s*=\s*new\s*Hashtable\s*<\s*>\(\s*\);\s*[a-zA-Z_][a-zA-Z0-9_]*\.put\s*\(\s*Context\.PROVIDER_URL,\s*("[^"]*ldap://[^"]*")\s*\);
```

```
\bHashtable\s*<\s*String,\s*String\s*>\s*[a-zA-Z_][a-zA-Z0-9_]*\s*=\s*new\s*Hashtable\s*<\s*>\(\s*\);\s*[a-zA-Z_][a-zA-Z0-9_]*\.put\s*\(\s*Context\.PROVIDER_URL,\s*("[a-zA-Z_][a-zA-Z0-9_]*")\s*\);
```

## Owasp-Mobile: M5 Insecure Communication
