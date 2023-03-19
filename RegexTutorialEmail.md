# Regex Tutorial for Emails

Hello GitHub! My name is Spencer Fields and I am currently attending the UT Austin Coding Academy to learn several different aspects of web development to further my knowledge in a new and growing interest of mine. I am always open to any constructive criticism and look forward to learning together!

## Summary

Below I will be outlining the functionality of a regular expression that can be used to identify emails:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  

I will look at each part of the regex and decipher what it is including and/or omitting from the criteria.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The anchors used in the email regex above are the caret  `^` and dollar sign `$`, which are used to open and close the string. In the expression above, the `^` is denoting that the string begins with the characters following the `^` symbol. The `$` anchor is telling us that the string will end with the characters appearing before the `$` anchor. 

In this case, the string is beginning with the information included in the bracket `([a-z0-9_\.-]+)` and it ends with `[a-z\.]`, which is the information preceding the quantifier `{2,6}.`

Essentially, the string above can start with any lowercase letters `a-z` any number `0-9` an underscore `_` a dot `.`, which is using a `\` prior to escape the default meaning `\.` and a hyphen `-`. The string can end with any lowercase letters `a-z` and a dot `\.`. You can see that the information before the `$` anchor represents the common formatting of domain names such as `email.com.`

### Quantifiers

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Immediately preceding the `$` anchor the regex expression has `{2,6}.` This is a quantifier that is communicating the amount of matches that can be included. Here it is saying between 2 and 6 matches. Some common use cases are presented below:

`{2}` would represent exactly 2 matches  
`{2, }` would represent a minimum of 2 matches  
`{2,6}` would represent between 2 and 6 matches

### Grouping Constructs

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The expression above includes a capturing grouping construct which is represented by the enclosing parenthesis around each group. There are three groups being captured as follows: `/^(Group 1)@(Group 2).(Group 3)$/`. The whole expression is represented by `Group 0.` Grouping constructs can be useful for many things such as reordering information using `$(Group Number)` syntax.

For example, if you only wanted to view the domain names to see how many users are using each domain you could find and replace using only groups 2 and 3.

### Bracket Expressions

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Bracket expressions help to communicate the specific characters and/or symbols to allow or omit in the expression. I will decipher each bracket by breaking up each group below:

Group 1 

`([a-z0-9_\.-]+)`
allows lowercase letters from a to z `a-z`, any digits from 0 to 9 `0-9`, underscores `_`, dots `\.`, and hyphens `-`. Note that the period includes a backslash `\` before it to escape the default behavior of the dot `.`. The plus sign `+` indicates that it can be any length, but it must be at least 1.

Group 2

`([\da-z\.-]+)` 
allows digits `\d`, lowercase letters `a-z`, dots `\.`, and hyphens `-`. The plus sign `+` indicates that it can be any length, but it must be at least 1.

Group 3

`([a-z\.]{2,6})` 
allow lowercase letters `a-z`, dots `\.`, and between 2 and 6 `{2,6}` characters.

### Character Classes

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Bracket expressions represent a positive character group indicating that the expression will contain what is included in the brackets in the expression.
The `/d` in Group 2 is representing a character class that includes digits, which is simply another way to write the `0-9` from Group 1.

### Character Escapes

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Character escapes are represented with a backslash `\` which indicates the intent to use the exact character or symbol as opposed to the default regex functionality. For example, in the regex above the character escape for the dot `\.` is used in every group indicating that the intent is to use the period instead of the regex matching functionality.

## Author

Spencer Fields is a new and aspiring programmer that is currently attending the UT Austin Coding Academy Fullstack Web Development program.