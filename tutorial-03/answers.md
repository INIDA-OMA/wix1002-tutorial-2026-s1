# Tutorial 03 — Answers

WIX1002 Fundamentals of Programming: Flow of Control (Selection)

## Question 1 — Write statements

### a. Determine whether `3 × 8 = 27`

```java
System.out.println(3 * 8 == 27);
```

Output: `false`.

### b. Determine whether an integer is odd or even

Assume `number` has already been read as an `int`.

```java
if (number % 2 == 0) {
    System.out.println("Even");
} else {
    System.out.println("Odd");
}
```

An even integer has remainder zero when divided by 2.

### c. Determine whether a character is a capital letter

Assume `letter` is a `char`. This checks the English uppercase range A through Z.

```java
if (letter >= 'A' && letter <= 'Z') {
    System.out.println("Capital letter");
} else {
    System.out.println("Not a capital letter");
}
```

### d. Display two strings in alphabetical order, ignoring case

Assume `first` and `second` are initialized `String` variables. `compareToIgnoreCase` compares without regard to uppercase/lowercase. If the strings are equal ignoring case, this prints `first` first.

```java
if (first.compareToIgnoreCase(second) <= 0) {
    System.out.println(first);
    System.out.println(second);
} else {
    System.out.println(second);
    System.out.println(first);
}
```

### e. Display day name using a `switch`

Assume `day` is an integer from 0 to 6, where 0 is Sunday. The PDF spells the last day “Satudary”; the intended weekday is Saturday.

```java
switch (day) {
    case 0:
        System.out.println("Sunday");
        break;
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    case 4:
        System.out.println("Thursday");
        break;
    case 5:
        System.out.println("Friday");
        break;
    case 6:
        System.out.println("Saturday");
        break;
    default:
        System.out.println("Invalid day number");
}
```

Each `break` stops execution from falling through into the following case.

## Question 2 — Correct the statements

### a. Compare two numbers

Use `==` to compare values. A single `=` assigns a value.

```java
if (num1 == num2) {
    System.out.println("Number 1 is equal to number 2.");
}
```

### b. Check whether `x` is greater than both `y` and `z`

Java does not support chained comparisons such as `x > y > z`. Join two comparisons with `&&`.

```java
if (x > y && x > z) {
    System.out.println("x is the largest number");
}
```

This condition requires `x` to be strictly larger than both other numbers. Ties are not reported as a unique largest value.

### c. Compare two strings by content

Use `.equals()` to compare string contents. The original `else (condition)` is invalid; an `else if` needs an `if` condition, while this case needs a plain `else`.

```java
String s1 = "hello";
String s2 = "world";

if (s1.equals(s2)) {
    System.out.println("They are equal strings.");
} else {
    System.out.println("They are not equal strings.");
}
```

The example values initialize the strings so this fragment can run. Replace them with the strings to compare.

### d. Test whether either number is positive

Use Java's logical OR operator `||`, and put the condition in parentheses.

```java
if (x > 0 || y > 0) {
    System.out.println("Either x or y is positive");
}
```

## Question 3 — Write the output when `x = 9` and `y = 10`

### a.

The `else` belongs to the nearest unmatched `if`, which is `if (y > 10)`. The outer condition is true, the inner condition is false, then the final print runs unconditionally.

```text
#####
$$$$$
```

### b.

The outer condition is true. The inner condition `y < 10` is false, so the `else` block prints both lines.

```text
#####
$$$$$
```

### c.

The outer condition is true. The inner condition is false, so `*****` is skipped. `#####` is still inside the outer block and prints. The outer `else` is skipped.

```text
#####
```

### d.

The first condition, `x > 10`, is false, so the whole block is skipped.

```text
No output
```

## Question 4 — Find the biggest of three integers

This solution reports the maximum value. If values tie, it still reports the shared maximum; it does not identify a unique number.

### Java statements

```java
int largest = a;

if (b > largest) {
    largest = b;
}
if (c > largest) {
    largest = c;
}

System.out.println("The biggest number is " + largest);
```

Here `a`, `b`, and `c` are assumed to be integers already read from the user.

## Question 5 — Determine whether a year is a leap year

A year is a leap year when it is divisible by 400, or when it is divisible by 4 but not by 100. The divisibility-by-400 rule makes century years such as 2000 leap years, while 1900 is not.

### Java statements

```java
if (year % 400 == 0 || (year % 4 == 0 && year % 100 != 0)) {
    System.out.println("Leap year");
} else {
    System.out.println("Not a leap year");
}
```

Here `year` is an integer already read from the user. Examples: `2000` is a leap year; `1900` is not; `2024` is a leap year.
