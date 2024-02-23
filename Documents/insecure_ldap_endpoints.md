# Insecure Ldap Endpoints

Insecure LDAPS Endpoint Configuration. Using insecure LDAPS can lead to the transmission of sensitive information over
unencrypted connections, posing a significant security risk.

---

### CWE Reference: CWE-297

## Patterns

```
import javax.naming.Context;
import javax.naming.NamingException;
import javax.naming.directory.InitialDirContext;
import java.util.Hashtable;

public class LdapContextExample {
    public static void main(String[] args) {
        // Matched line of code
        Hashtable<String, String> env = new Hashtable<>();
        env.put(Context.INITIAL_CONTEXT_FACTORY, "com.sun.jndi.ldap.LdapCtxFactory");
        env.put(Context.PROVIDER_URL, "ldap://example.com:389");

        try {
            InitialDirContext context = new InitialDirContext(env);

            // Additional code for illustration
            // ...
        } catch (NamingException e) {
            e.printStackTrace();
        }
    }
}
```

## Regex

```
new InitialLdapContext\s*\(\s*.*,\s*null\s*\);
```