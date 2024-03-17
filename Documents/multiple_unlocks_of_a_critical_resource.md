# Multiple unlocks of a critical resource

---

When the product is operating in a concurrent environment and repeatedly unlocks a critical resource, the consequences
will vary based on the type of lock, the lock's implementation, and the resource being protected. In some situations
such as with semaphores, the resources are pooled and extra calls to unlock will increase the count for the number of
available resources, likely resulting in a crash or unpredictable behavior when the system nears capacity.

### CWE Reference: CWE-765

## Patterns

```
// Assuming "lock" is an instance of a lock or mutex
lock.lock();
try {
    // Code block protected by the lock
} finally {
    lock.unlock();
    // Additional code
    lock.unlock();
}
```

## Regex

```
(lock\.lock\(\);[\s\S]*?lock\.unlock\(\);[^\}]*?lock\.unlock\(\);)
```

## Owasp-Mobile: M8 Security Misconfiguration
