# Regex with Python

Regular expressions, commonly known as regex, are powerful tools used in text processing to find, match, and manipulate strings based on specific patterns. In this tutorial, we will explore the fundamentals of regular expressions in Python and learn how to use them effectively.

## Summary

In this tutorial, we will cover the basics of regular expressions in Python by explaining various components and constructs commonly used in regex patterns. We will focus on real-world examples and provide code snippets to demonstrate each concept.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
The characters ^ and $ are both anchors. The ^ anchor signifies a string that begins with the characters that come after it. The $ anchor signifies a string that ends with the characters that precede it. Essentially the ^ is the beginning and the
$ is the end of the string. These match positions in the text versus matching specific characters. The function 'import re' is pythons method of importing the module needed to execute regular expression functions. 

^ (Caret): This anchor is used to match the beginning of a string. It ensures that the pattern following the caret appears at the very start of the string. For example, ^Hello will match strings that start with "Hello".

$ (Dollar Sign): This anchor is used to match the end of a string. It ensures that the pattern preceding the dollar sign appears at the very end of the string. For example, World$ will match strings that end with "World".

import re

Example: Matching strings starting with "Hello"
pattern = r"^Hello"
text = "Hello, world!"
result = re.search(pattern, text)
print(result.group())  # Output: "Hello"

### Quantifiers
Quantifiers are used to specify the number of characters. Quantifiers such as * (zero or more), + (one or more), ? (zero or one), and {} (exact count).

'*' (Asterisk): This quantifier matches zero or more occurrences of the preceding character or group. For example, a* will match zero or more "a" characters.

'+' (Plus): This quantifier matches one or more occurrences of the preceding character or group. For example, a+ will match one or more "a" characters.

'?' (Question Mark): This quantifier matches zero or one occurrence of the preceding character or group. For example, colou?r will match both "color" and "colour".

'{}' (Curly Braces): This quantifier allows you to specify an exact number of occurrences. For example, a{3} will match exactly three consecutive "a" characters.
import re

Example: Matching repeated characters
pattern = r"a{3}"
text = "aaaabc"
result = re.search(pattern, text)
print(result.group())  
Output: "aaa"

### Grouping Constructs
Grouping constructs allow us to treat multiple characters as a single unit rather than individual pieces. 
Parentheses () are used to create groups and apply quantifiers or other operators to them.

'(ab){2}': This grouping construct matches the sequence "ab" occurring exactly twice in a row.

import re

Example: Matching a pattern with grouping
pattern = r"(ab){2}"
text = "ababab"
result = re.search(pattern, text)
print(result.group())  
Output: "abab"

### Bracket Expressions
Bracket expressions are also known as character classes. These allow us to match any character within a specified set.
Square brackets [] are used to define character classes.

'[aeiou]': This character class matches any of the characters "a", "e", "i", "o", or "u".

import re

Example: Matching vowels using character classes
pattern = r"[aeiou]"
text = "Hello, World!"
result = re.findall(pattern, text)
print(result) 
Output: ['e', 'o', 'o']

### Character Classes
Character classes provide shortcuts to match common sets of characters such as:

\d: This character class matches any digit (0-9).
\w: This character class matches any alphanumeric character (letters, digits, and underscores).
\s: This character class matches any whitespace character (spaces, tabs, line breaks, etc.).

import re

# Example: Matching a date pattern using character classes
pattern = r"\d{2}-\d{2}-\d{4}"
text = "Today's date is 27-07-2023"
result = re.search(pattern, text)
print(result.group())  
Output: "27-07-2023"

### The OR Operator
The OR operator '|' allows to match two patterns. 

'cat|dog': This pattern will match either "cat" or "dog". For example, in the string "I have a cat and a dog", both "cat" and "dog" would be matched.

import re

Example: Matching multiple alternatives using the OR operator
pattern = r"cat|dog"
text = "I have a cat and a dog"
result = re.findall(pattern, text)
print(result)  
Output: ['cat', 'dog']

### Flags
Flags are optional modifiers that you can use to change how the regex engine interprets the pattern:
're.IGNORECASE': This flag makes the pattern matching case-insensitive. For example, with the pattern hello, it would match both "hello" and "Hello".

import re

Example: Case-insensitive matching using flags
pattern = r"hello"
text = "HELLO, World!"
result = re.search(pattern, text, re.IGNORECASE)
print(result.group())  
Output: "HELLO"

### Character Escapes
Character escapes are used to match special characters as literal characters. 
'\.': This escape sequence matches a literal dot. For example, it would match the dot in https://github.com/kolelam

import re

Example: Matching a literal dot using character escape
pattern = r"\."
text = "https://github.com/kolelam"
result = re.search(pattern, text)
print(result.group())  
Output: "."

## Author
This tutorial was written by Kole Lam, a student at edX's coding bootcamp (https://github.com/kolelam)