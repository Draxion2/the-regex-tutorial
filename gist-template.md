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

Regex classes are `\s`, `\d`, `\w`, and `.`

_Regex Examples_
* `\s`: matches a whitespace character
* `\d`: matches any character that is a digit
* `\w`: matches any word character, including underscores
* `.`: matches any character

These perform inverse matches<br>
_Negeted Character Classes_
* `\S`: matches a non-whitespace character
* `\D`: matches a single non-digit character
* `\W`: matches any non-word character

It should be noted, however, when using the `.` operator to tread carefully cause often character classes or negated character classes are faster.

Lets print the regex at the top of the page down here and take a closer look at it.<br>
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

As you can see the character classes that exist in this regex are `\d` and `.`. When studying their locations, it can be seen that the sequence is looking for any character that matches a digit followed by any character that is between 'a' and 'z'. The `.` matches any character, regardless of wether its a letter, number, or even a special character.

### Flags

Regex flags are `//`, `/g`, `/i`, `/m`

_Regex Example_
* `/email/`: means the search happens in between the `/`
* `/email/g`: 'g' means 'global', which does not return the first match
* `/email/m`: 'm' means 'multi-line', which will start and end on a line not the whole string
* `/eMaIl/i`: 'i' means 'insensitive'. It makes the entire expression case-insensitive. This example would match `EmAiL`

Even though the email regex doesn't present any of the `/g`, `/i`, and `/m` flags, it does present `/` at the start and finish, which means it will search everything in between. Typically every regex has this important concept.

### Grouping and Capturing

Regex grouping and capturing are `()`

_Regex Examples_
* `e(mail)`: the parentheses present a capturing group with the value 'mail'
* `e(?:mail)`: when using the `?:` it disables the capturing group
* `e(?<custom_name>mail)`: when using `?<custom_name>` it allows us to put a name to the group. 'custom_name' can be anything you it to be

In the email regex at the top of the page, we are presented with 3 capturing groups.
* `([a-z0-9_\.-]+)`
* `([\da-z\.-]+)`
* `([a-z\.]{2,6})`

This is extremely useful when needing to take information for strings and/or data using a preferred programming language.

### Bracket Expressions

Regex bracket expressions are `[]`

_Regex Examples_
* `[email]`: this matches a string which has either 'e', 'm', 'a', 'i', or 'l'. This sequence is equal to `e|m|a|i|l` or `[e-m]`
* `[0-9]`: matches a string that has between 0 and 9
* `[e-mE-m]`: this matches a string that is either lowercase e-m and/or uppercase E-M

Returning back to the lengthy regex above, we are presented with 3 bracket expressions.
`[a-z0-9_\.-]`<br>
This group will match a string that contains any character or number, along with any special characters because of the character class `.`<br>
`[\da-z\.-]`<br>
This group will match any string that contains any character after a digit because of the character class `\d`. It will then match any character after because of the `.`.<br>
`[a-z\.]`<br>
This group will match any character, regardless of being a letter, number, or special character

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
