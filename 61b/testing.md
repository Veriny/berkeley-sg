---
description: Adapted from 61B's coursework.
---

# Testing

## Test-Driven Development

* Identify a new feature, and write a unit test for it.
* Run the failing test.
* Write code that passes the test
* Refactor the code, making it faster, easier to read, or accounting for more cases.

## Testing in Java

Testing in Java is simple using the JUnit library. Here is an example of a possible test.

```text
@org.jnunit.Test
public void testMethod() {
    Object[] input = {"before"};
    Object[] expected = {"after"};
    method(input);
    org.junit.Assert.assertArrayEquals(expected, input);
}
```

The test above would be a possible one for a method that mutates an array to something else. 

{% hint style="warning" %}
Tests using JUnit may not be static methods.
{% endhint %}

Using Intellij, these tests can be run individually or all at once. Combined with the debugger, students can avoid "autograder driven development," which entails of basically relying on the autograder to churn out code that will, eventually, be correct.

You can run these tests all at once or individually in IntelliJ.

