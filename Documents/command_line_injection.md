# Command Line Injection

Uncontrolled command line. Potential for unauthorized execution of commands, leading to serious security risks.

---

### CWE Reference: CWE-74

## Patterns

```
// Example: Concatenating user input into a command without proper validation
String userInput = getUserInput();
String command = "runScript.sh " + userInput;
Runtime.getRuntime().exec(command);
```

## Regex

```
Runtime\.getRuntime\(\)\.exec\(".*?"\s*\+\s*userInput\s*\+\s*".*?"\);
```