# **EXP. NO. 6: AI-Assisted Programming and Debugging**

## **1. Date**

26-11-2026

## **2. Register Number**
 212225040177

## **3. Aim**

To write and implement programs using multiple AI tools, identify and debug errors, optimize code, analyse time and space complexity, generate unit tests, and compare manual programming with AI-assisted programming.

## **4. AI Tools Required**

- ChatGPT – code generation, debugging, and explanation.
- Google Gemini – alternative code generation and code review.
- Python 3, a C compiler, and a Java compiler – program execution and testing.

## **5. Explanation**

AI-assisted programming uses artificial intelligence tools to generate, analyse, debug, and optimize source code. In this experiment, the same programming problem is solved using Python, C, and Java. AI-generated solutions are compared based on correctness, code quality, efficiency, and maintainability.

**Selected application:** Find the largest digit in a given positive integer.

## **6. Problem Statement**

Write a program to find the largest digit in a given integer. Generate implementations in Python, C, and Java using AI tools, test the programs, identify possible bugs, optimize the code, and compare their performance and quality.

**Sample input:**

```
987465
```

**Expected output:**

```
The largest digit is 9
```

## **7. Procedure**

1. Select the programming problem.
2. Enter a role-based programming prompt into ChatGPT.
3. Generate the solution in Python, C, and Java.
4. Review the code using Google Gemini or another AI tool.
5. Identify potential bugs and correct them.
6. Optimize the code and analyse time and space complexity.
7. Generate unit test cases and execute them.
8. Compare manual coding and AI-assisted coding.
9. Record the observations and conclusion.

## **8. Prompt Used**

Act as an experienced software programmer and debugging engineer. Write a program to find the largest digit in a given positive integer using Python, C, and Java.

For each language:

1. Generate correct and readable code.
2. Identify possible bugs and edge cases.
3. Optimize the implementation.
4. Explain time and space complexity.
5. Generate at least five test cases with expected outputs.
6. Compare the solutions based on correctness, efficiency, readability, and maintainability.

Do not invent test execution results. Explain the expected results and mention any assumptions.

## **9. Program Implementation**

### **A. Python Program**

```
def largest_digit(n):    n = abs(n)    largest = 0    while n > 0:        digit = n % 10        if digit > largest:            largest = digit        n //= 10    return largestnum = int(input())print("The largest digit is", largest_digit(num))
```

**Sample output:**

```
987465
The largest digit is 9
```

### **B. C Program**

```
#include <stdio.h>

int main(void) {
    long long n;
    int digit, largest = 0;

    scanf("%lld", &n);

    if (n < 0)
        n = -n;

    while (n > 0) {
        digit = n % 10;

        if (digit > largest)
            largest = digit;

        n /= 10;
    }

    printf("The largest digit is %d\n", largest);

    return 0;
}
```

**Sample output:**

```
987465
The largest digit is 9
```

*Note:* This basic C implementation assumes the input is within a range that can be safely negated by `long long`. The minimum representable `long long` value requires special handling.

### **C. Java Program**

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        long n = sc.nextLong();
        n = Math.abs(n);

        int largest = 0;

        while (n > 0) {
            int digit = (int) (n % 10);

            if (digit > largest) {
                largest = digit;
            }

            n /= 10;
        }

        System.out.println("The largest digit is " + largest);
        sc.close();
    }
}
```

**Sample output:**

```
987465
The largest digit is 9
```

## **10. Bug Identification and Debugging**

Consider the following incorrect Python code:

```
n = 987465largest = 0while n > 0:    digit = n % 10    largest = digit    n //= 10print(largest)
```

**Bug:** The statement `largest = digit` replaces the current largest digit during every iteration instead of comparing the digits.

**Corrected statement:**

```
if digit > largest:    largest = digit
```

The corrected program compares each digit with the largest digit found so far. For the input `987465`, the correct output is `9`.

Other potential issues include handling zero, negative inputs, invalid input, and numeric overflow in languages with fixed-width integer types.

## **11. Code Optimization**

The optimized approach processes each digit once using the modulo and integer division operators.

- `% 10` extracts the last digit.
- `// 10` in Python, or integer division in C and Java, removes the last digit.
- A comparison updates the maximum digit.

This approach avoids converting the number into a string or storing digits in an array.

## **12. Time and Space Complexity**

Let \\(d\\) represent the number of digits in the input integer.

| Language | Time complexity | Auxiliary space |
| -------- | --------------- | --------------- |
| Python   | \\(O(d)\\)      | \\(O(1)\\)      |
| C        | \\(O(d)\\)      | \\(O(1)\\)      |
| Java     | \\(O(d)\\)      | \\(O(1)\\)      |

All three implementations process each digit once and use a constant number of variables.

## **13. Unit Testing**

| Test case | Input  | Expected output |
| --------- | ------ | --------------- |
| 1         | 987465 | 9               |
| 2         | 12345  | 5               |
| 3         | 1111   | 1               |
| 4         | 90807  | 9               |
| 5         | 0      | 0               |
| 6         | 56789  | 9               |

These are expected results derived from the algorithm; they should be confirmed by executing the programs. The implementations above support zero, and Python and Java handle negative inputs by taking the absolute value, subject to Java's minimum `long` edge case.

## **14. Comparison of AI Tools**

| Evaluation criterion | ChatGPT                                         | Google Gemini                            |
| -------------------- | ----------------------------------------------- | ---------------------------------------- |
| Code generation      | Generates implementations in multiple languages | Can generate alternative implementations |
| Bug detection        | Can identify logic errors and edge cases        | Can review logic and suggest corrections |
| Optimization         | Explains efficient algorithms                   | Can suggest alternative approaches       |
| Complexity analysis  | Explains time and space complexity              | Can provide complexity analysis          |
| Unit testing         | Can generate test cases                         | Can generate test cases                  |

*Observation:* This is a qualitative comparison of the tools' capabilities, not a measured head-to-head benchmark. Both tools may produce incorrect code, so their outputs must be compiled, executed, and verified.

## **15. Manual Coding vs AI-Assisted Coding**

| Factor            | Manual coding                             | AI-assisted coding                 |
| ----------------- | ----------------------------------------- | ---------------------------------- |
| Coding speed      | Depends on experience                     | Often faster for routine tasks     |
| Debugging         | Requires manual investigation             | AI can suggest likely errors       |
| Learning          | Builds independent problem-solving skills | Provides explanations and examples |
| Accuracy          | Depends on programmer skill               | Requires independent verification  |
| Code optimization | Requires algorithm knowledge              | Can suggest optimization ideas     |
| Testing           | Tests must be designed manually           | Can generate test cases quickly    |

## **16. Code Quality Analysis**

The three implementations use simple loops, clear variable names, and constant auxiliary space. Their basic algorithm is efficient for finding the largest digit.

However, the C and Java implementations have fixed-width integer limits, and robust applications should validate input and handle extreme values safely. AI-generated code is useful as a starting point, but compilation, testing, and manual review are necessary before deployment.

## **17. Conclusion**

AI-assisted programming helps developers generate code in multiple languages, identify logical errors, improve implementations, analyse complexity, and create unit tests. Comparing AI-assisted and manual coding shows that AI can reduce routine development effort, while human verification remains essential for correctness and reliability.

## **RESULT**

The experiment was executed successfully by developing Python, C, and Java programs to find the largest digit in a number, analysing potential bugs, optimizing the algorithm, studying time and space complexity, and preparing unit tests. The comparison demonstrated the usefulness of AI tools in programming and debugging.
