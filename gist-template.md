# Regex Tutorial Gist

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

Anchors are used to match a pattern at a specific position in the input string. The most commonly used anchors are `^` and `$`. The caret `^` matches the start of a line, while the dollar sign `$` matches the end of a line.

```
const regex = /^hello$/;
console.log(regex.test("hello")); // true
console.log(regex.test("hello world")); // false
console.log(regex.test("say hello")); // false
```

### Quantifiers

Quantifiers specify how many times a character or group should be matched. The most commonly used quantifiers are `*`, `+`, `?`, and `{}`. The asterisk `*` matches zero or more occurrences of the preceding character or group. The plus sign `+` matches one or more occurrences of the preceding character or group. The question mark `?` matches zero or one occurrence of the preceding character or group. The curly braces `{}` can be used to specify a specific number of occurrences.

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

The OR operator, denoted by the vertical bar `|`, matches one of two or more alternatives. It has the lowest precedence of all regex operators.

```
const regex = /cat|dog/;
console.log(regex.test("cat")); // true
console.log(regex.test("dog")); // true
console.log(regex.test("bird")); // false
```

### Character Classes

Character classes are used to match a set of characters. They are enclosed in square brackets `[]`. The most commonly used character classes are `\d`, `\w`, and `\s`. The backslash before the character specifies a special character class. For example, `\d` matches any digit from 0 to 9.

```
const regex = /[aeiou]/;
console.log(regex.test("apple")); // true
console.log(regex.test("banana")); // true
console.log(regex.test("pear")); // false

const regex2 = /\d{3}-\d{2}-\d{4}/;
console.log(regex2.test("123-45-6789")); // true
```

### Flags

Flags that modify the behavior of the pattern matching. The `g` flag enables global search, which finds all occurrences of the pattern in the string instead of just the first one. The `i` flag enables case-insensitive search, which matches both uppercase and lowercase characters. The `m` flag enables multiline search, which matches the pattern at the beginning or end of each line in a multiline string. The s flag enables dotall search, which matches any character including newline characters.

```
// match all occurrences of a pattern with the 'g' flag
const pattern = /\d+/g;
const str = 'I have 2 apples and 3 bananas';
const matches = str.match(pattern);
console.log(matches); // ['2', '3']

// match a pattern case-insensitively with the 'i' flag
const pattern2 = /apple/i;
console.log(pattern2.test('Apple')); // true
console.log(pattern2.test('banana')); // false

// match a pattern that spans multiple lines with the 'm' flag
const pattern3 = /^hello/m;
const str3 = 'hello world\nhello there';
const matches3 = str3.match(pattern3);
console.log(matches3); // ['hello', 'hello']

// match any character including newline characters with the 's' flag
const pattern4 = /hello.world/s;
const str4 = 'hello\nworld';
console.log(pattern4.test(str4)); // true
```

### Grouping and Capturing

Grouping and Capturing use parentheses `()` to group and capture parts of a pattern. Grouping can be used to apply quantifiers to a group of characters, while capturing can be used to extract a specific part of the match. Captured groups are numbered from left to right based on the order of the opening parentheses in the pattern. The captured text can be accessed using the `exec` method or the `match` method of the string.

```
// match a string that contains a repeated word
const pattern = /\b(\w+)\b\s+\1\b/g;
const str = 'this is a a test test';
const matches = str.match(pattern);
console.log(matches); // ['a a', 'test test']

// extract the username and domain from an email address
const pattern2 = /^(\w+)@([\w.]+)$/;
const email = 'johndoe@example.com';
const match = email.match(pattern2);
console.log(match); // ['johndoe@example.com', 'johndoe', 'example.com']
console.log(match[1]); // 'johndoe'
console.log(match[2]); // 'example.com'
```

### Bracket Expressions

Bracket expressions (also known as character classes) to match any character from a specified set. Bracket expressions are enclosed in square brackets `[]` and can include any combination of characters, ranges, and predefined character classes. A range of characters can be specified using a hyphen `-` between the start and end characters. Predefined character classes represent common sets of characters, such as digits, alphabetic characters, and whitespace. The caret `^` can be used inside the bracket expression to match any character that is not in the set.

Example:

```
// match a string that starts with any vowel
const pattern = /^[aeiou]/;
const str = 'apple banana cat';
const match = str.match(pattern);
console.log(match); // ['a']

// match a string that contains any digit
const pattern2 = /\d+/g;
const str2 = 'I have 2 apples and 3 bananas';
const matches2 = str2.match(pattern2);
console.log(matches2); // ['2', '3']

// match a string that contains only alphabetic characters and spaces
const pattern3 = /^[a-zA-Z\s]+$/;
const str3 = 'hello world';
const match3 = str3.match(pattern3);
console.log(match3); // ['hello world']

// match a string that contains any character except digits
const pattern4 = /[^\d]+/g;
const str4 = 'I have 2 apples and 3 bananas';
const matches4 = str4.match(pattern4);
console.log(matches4); // ['I have ', ' apples and ', ' bananas']
```

### Greedy and Lazy Match

Greedy and lazy quantifiers are used to control the amount of text matched by a pattern. Greedy quantifiers match as much text as possible while still allowing the overall pattern to match. Lazy quantifiers, on the other hand, match as little text as possible while still allowing the overall pattern to match. Greedy quantifiers are represented by `+`, `*`, and `?` metacharacters, while lazy quantifiers are represented by `+?`, `*?`, and `??` metacharacters.

```
// match a string that starts with a quote and ends with the same quote
const pattern = /".+"/g;
const str = 'He said, "Hello world" and she said, "Goodbye"';
const matches = str.match(pattern);
console.log(matches); // ['"Hello world" and she said, "Goodbye"']

// match a string that starts with a quote and ends with the same quote (lazy version)
const pattern2 = /".+?"/g;
const matches2 = str.match(pattern2);
console.log(matches2); // ['"Hello world"', '"Goodbye"']
```

### Boundaries

Boundary matchersare used to match patterns at specific positions in a string. The `^` metacharacter matches the beginning of a string or the beginning of a line in a multiline string. The `$` metacharacter matches the end of a string or the end of a line in a multiline string. The `\b` metacharacter matches a word boundary between a word character and a non-word character. The `\B` metacharacter matches a non-word boundary between two word characters.

```
// match a pattern at the beginning or end of a string
const pattern1 = /^hello/;
const str1 = 'hello world';
console.log(pattern1.test(str1)); // true

const pattern2 = /world$/;
const str2 = 'hello world';
console.log(pattern2.test(str2)); // true

// match a pattern at a word boundary
const pattern3 = /\bapple\b/;
console.log(pattern3.test('I like apples')); // true
console.log(pattern3.test('I like pineapple')); // false

// match a pattern at a non-word boundary
const pattern4 = /\Btree\B/;
console.log(pattern4.test('street')); // true
console.log(pattern4.test('tree')); // false
```

### Back-references

A back-reference is denoted by `\n`, where `n` is the index of the captured group. The index starts at 1 for the first captured group and increases by 1 for each additional captured group.

```
// match a repeated word using a back-reference
const pattern1 = /\b(\w+)\s+\1\b/;
console.log(pattern1.test('hello hello')); // true
console.log(pattern1.test('hello world')); // false

// replace a repeated word with a different word using a back-reference
const pattern2 = /\b(\w+)\s+\1\b/;
const str2 = 'hello hello world';
const newStr2 = str2.replace(pattern2, '$1 again');
console.log(newStr2); // 'hello again world'
```

### Look-ahead and Look-behind

## Author

Chris Lemmon, a junior web developer [@theLemmonade](https://github.com/theLemmonade).