# Demystifying the Regex

Regular expressions, often abbreviated as regex, are a cornerstone in text processing, offering a robust method to match, extract, and manipulate strings. Today, we'll dive deep into a specific regex pattern tailored for validating North American phone numbers.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Summary

Regular Expressions, commonly known as regex or regexp, are a powerful tool for text processing. Their roots trace back to formal language theory and mathematical notation from the 1950s.

1950s: The foundational concepts of regex were introduced by mathematician Stephen Kleene. He developed regular expressions as a notation to describe Neville Rabiner's mathematical model of a regular set. This notation was then used in early computer science for lexical analysis in compilers.

1970s: The Unix operating system played a pivotal role in popularizing regex. Tools like ed, sed, and grep incorporated regex capabilities, allowing users to perform complex text manipulations.

1980s and 1990s: As computing evolved, so did regex. Programming languages like Perl integrated enhanced regex capabilities, making them a staple for text processing tasks. This period also saw the introduction of PCRE (Perl Compatible Regular Expressions), which further expanded the reach and capabilities of regex.

2000s to Present: Today, nearly all modern programming languages, from JavaScript to Python, support regex in some form. They have become an indispensable tool for tasks ranging from data validation to web scraping.

Lets see for example how it works for Hex Codes. Matching a hex value, especially in the context of web colors, is a common use case for regex. Let's break down the regex pattern `^#?([a-f0-9]{6}|[a-f0-9]{3})$` to understand how it matches hex values:

## Regex Breakdown

### Anchors

- `^`: This matches the start of a line or string. It ensures that the pattern matches right from the beginning of the input.

- `$`: This matches the end of a line or string. It ensures that the pattern matches until the very end of the input.

Together, `^` and `$` ensure that the entire input string conforms to the pattern between them.

### Quantifiers

- `?`: Matches zero or one of the preceding token, making it optional. In this regex, it means the hash `#` character is optional.

- `{6}` and `{3}`: These match exactly six and three of the preceding token, respectively. In the context of this regex, they're used to match either a 3-digit or 6-digit hex value.

### Bracket Expressions

- `[a-f0-9]`: This matches any single character that is a digit from `0` to `9` or a lowercase letter from `a` to `f`. Hexadecimal values are base-16, so they can include numbers 0-9 and letters a-f.

### Grouping Constructs

- `(...)`: This is a capturing group. It groups multiple tokens together and captures the matched segment. In this regex, it's used to group the alternative patterns for 3-digit and 6-digit hex values.

### The OR Operator

- `|`: Acts as an OR operator. It matches either the pattern before it or the pattern after it. In this regex, it's used to match either a 3-digit hex value (`[a-f0-9]{3}`) or a 6-digit hex value (`[a-f0-9]{6}`).

## Summary

The regex `^#?([a-f0-9]{6}|[a-f0-9]{3})$` can be read as:

1. Start of the string (`^`).
2. Optionally a hash character (`#?`).
3. Either:
   - Six characters that are digits or lowercase letters a-f (`[a-f0-9]{6}`), or
   - Three characters that are digits or lowercase letters a-f (`[a-f0-9]{3}`).
4. End of the string (`$`).

This pattern effectively matches valid 3-digit or 6-digit hex color values, with or without a preceding hash character


Other components are, to mention a few:

### Character Classes

- `\d`: A shorthand to match any digit, equivalent to 0-9.

### Flags

While our regex doesn't utilize flags, it's worth noting some common ones: `i` for case-insensitive matching, `g` for global matching, and `m` for multiline matching.

### Character Escapes

- `\+`: Matches the plus sign literally.
- `\s`: Matches any whitespace character.
- `\(` and `\)`: These escape sequences match the opening and closing parentheses, respectively.



## Author

Written by le-shush, an architect and software developer passionate about technology, sustainability and design. For more insights and projects, visit [my Github profile](https://github.com/le-shush).
