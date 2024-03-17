# Path Injection

---

Uncontrolled data used in path expression. Path injection vulnerabilities can lead to serious security issues, allowing
attackers to manipulate file paths and potentially gain unauthorized access to sensitive resources.

### CWE Reference: CWE-73

## Patterns

```
// Example: Concatenating user input into a file path without proper validation
String userInput = getUserInput();
String filePath = "/uploads/" + userInput + "/file.txt";
File file = new File(filePath);
```

## Regex

```
new\s+File\s*\(\s*".*?"\s*\+\s*userInput\s*\+\s*".*?"\s*\);
```

## Owasp-Mobile: M4 Insufficient Input/Output Validation
