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

## Regex

```
FragmentTransaction\.replace\(.*,[^)]*Fragment\s*\.\s*class\s*\.
```