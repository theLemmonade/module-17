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

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
