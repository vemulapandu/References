# Fragment Injection

Android fragment injection. Fragment injection vulnerabilities can pose security risks by potentially allowing untrusted
input to manipulate fragment transactions.

---

### CWE Refernece: CWE-913

## Patterns

```
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentTransaction;

public class FragmentTransactionExample {
    public static void main(String[] args) {
        // Matched line of code
        FragmentTransaction transaction = getSupportFragmentManager().beginTransaction();
        transaction.replace(R.id.fragment_container, MyFragment.class, null);

        // Additional code for illustration
        // ...
    }
}
```

```
String fragmentClassName = "MyFragment";
Fragment myFragment = (Fragment) Class.forName(fragmentClassName).newInstance();
```

```
String fragmentClassName = userInputFromExternalSource;
Fragment myFragment = (Fragment) Class.forName(fragmentClassName).newInstance();
```

```
String fragmentClassName = userInputFromExternalSource;
if (isValidInput(fragmentClassName)) {
    Fragment myFragment = (Fragment) Class.forName(fragmentClassName).newInstance();
}
```

## Regex

```
transaction\.replace\(.*,[^)]*Fragment\s*\.\s*class\s*\w*
```

```
(?i)\bFragment\s+[a-zA-Z_][a-zA-Z0-9_]*\s*=\s*\(\s*Fragment\s*\)\s*Class\.forName\(\s*("[a-zA-Z_][a-zA-Z0-9_]*")\s*\)\.newInstance\(\s*\);
```

```
(?i)\bFragment\s+[a-zA-Z_][a-zA-Z0-9_]*\s*=\s*\(\s*Fragment\s*\)\s*Class\.forName\(\s*([a-zA-Z_][a-zA-Z0-9_]*)\s*\)\.newInstance\(\s*\);
```

```
(?i)\bFragment\s+[a-zA-Z_][a-zA-Z0-9_]*\s*=\s*\(\s*Fragment\s*\)\s*Class\.forName\(\s*([a-zA-Z_][a-zA-Z0-9_]*)\s*\)\.newInstance\(\s*\);
```

## Owasp-Mobile: M4 Insufficient Input/Output Validation
