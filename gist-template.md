# Email Validation Regex Tutorial

Greetings and welcome to my regex (regular expressions) tutorial. Regex is very useful in many coding languages by extracting information from any text or strings. It searches specifically through the string for one or more matches of search patterns.

## Summary

Today I will be instructing how to break down a regular expression and that one will be a method for code to validate if user input has a valid email address when submitting data via a server (i.e signing up for an application that needs an email).

Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

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

Regex anchors are `^` & `$`

_Regex Examples_
* `^email`: matches any string that starts with 'email'
* `com$`: matches any string that ends with 'com'
* `emailcom$`: has an exact string match, which starts and ends with 'emailcom'

If we look back at the regex posted above, these anchors are located at the start and end of the regex.

`/^` and `$/` means we are specifically looking for the start and end of a string.

### Quantifiers

Regex quantifiers are `?`, `{}`, `+`, and `*`

_Regex Examples_
* `email?`: matches a string that has 'emai' followed by 0 or 1 'email'
* `email{3}`: matches a string that has 'emai' followed by 3 'l'
* `email{3,}`: matches a string that has 'emai' followed by 3 or more 'l'
* `email{3,6}`: matches a string that has 'emai' followed by 3-6 'l'
* `email*`: matches a string that has 'emai' followed by 0 or more 'l'
* `email+`: matches a string that has 'emai' followed 1 or more 'l'

Refering back to our regex above, the following part of the syntax has some quantifiers.<br>
`([a-z0-9_\.-]+)` and `([a-z\.]{2,6})`

The `+` quantifer matches the same string followed by the group (we will learn what this means later in the tutorial).<br>
The `{2,6}` quantifer matches a string that contains 2-6 characters.

### OR Operator

Regex OR operators are `|` and `[]`

_Regex Examples_
* `ema(i|l)`: matches a string that has 'ema' followed by 'i' or 'l' (also captures 'i' or 'l')
* `ema[il]`: same as above, except 'i' and 'l' isn't captured

In the email regex above, there are OR operators present such as<br>
`[a-z0-9_\.-]` or `[\da-z\.-]`

Like in the regex examples mentioned earlier, the `[]` operator doesn't capture what is between the square brackets. Therefore when using this regex sequence, nothing is captured.

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
