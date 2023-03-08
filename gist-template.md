# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Regular expressions, or regex for short, are patterns used to match character combinations in strings. They are widely used in text processing applications such as search engines, text editors, and programming languages. A regular expression engine processes the pattern and attempts to match it against the input string. This gist covers the most commonly used regex features, including anchors, quantifiers, character classes, flags, grouping, and capturing.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors are used to match a pattern at a specific position in the input string. The most commonly used anchors are ^ and $. The caret ^ matches the start of a line, while the dollar sign $ matches the end of a line.

```
const regex = /^hello$/;
console.log(regex.test("hello")); // true
console.log(regex.test("hello world")); // false
console.log(regex.test("say hello")); // false
```

### Quantifiers

Quantifiers specify how many times a character or group should be matched. The most commonly used quantifiers are *, +, ?, and {}. The asterisk * matches zero or more occurrences of the preceding character or group. The plus sign + matches one or more occurrences of the preceding character or group. The question mark ? matches zero or one occurrence of the preceding character or group. The curly braces {} can be used to specify a specific number of occurrences.

```
const regex = /go+d/;
console.log(regex.test("god")); // true
console.log(regex.test("good")); // true
console.log(regex.test("gooood")); // true
console.log(regex.test("gd")); // false

const regex2 = /\d{3}-\d{2}-\d{4}/;
console.log(regex2.test("123-45-6789")); // true
```

### OR Operator

The OR operator, denoted by the vertical bar |, matches one of two or more alternatives. It has the lowest precedence of all regex operators.

```
const regex = /cat|dog/;
console.log(regex.test("cat")); // true
console.log(regex.test("dog")); // true
console.log(regex.test("bird")); // false
```

### Character Classes

Character classes are used to match a set of characters. They are enclosed in square brackets []. The most commonly used character classes are \d, \w, and \s. The backslash before the character specifies a special character class. For example, \d matches any digit from 0 to 9.

```
const regex = /[aeiou]/;
console.log(regex.test("apple")); // true
console.log(regex.test("banana")); // true
console.log(regex.test("pear")); // false

const regex2 = /\d{3}-\d{2}-\d{4}/;
console.log(regex2.test("123-45-6789")); // true
```

### Flags

Flags are special options that modify the behavior of the pattern matching. They are represented as one or more characters placed after the closing delimiter of the regular expression. Flags can be used to perform case-insensitive matching, global matching, and multiline matching. The most commonly used flags in Python are re.IGNORECASE (for case-insensitive matching), re.MULTILINE (for multiline matching), and re.DOTALL (for matching any character, including newlines). Flags can be passed as the second argument to the re.compile() function or as a third argument to the re.search() or re.match() functions.

```
import re

text = "The quick brown fox\nJumps over the lazy dog"

# match all occurrences of the word "the" regardless of case
pattern = re.compile(r"the", flags=re.IGNORECASE)
matches = pattern.findall(text)
print(matches)  # ['The', 'the']

# match the start and end of each line in the text
pattern = re.compile(r"^.*$", flags=re.MULTILINE)
matches = pattern.findall(text)
print(matches)  # ['The quick brown fox', 'Jumps over the lazy dog']

# match any character, including newlines
pattern = re.compile(r".*", flags=re.DOTALL)
match = pattern.match(text)
print(match.group(0))  # The quick brown fox\nJumps over the lazy dog
```

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
