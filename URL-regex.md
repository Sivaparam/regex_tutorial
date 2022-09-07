# Regular Expression - URL Validation
Regular Expression also called as regex is a sequence of characters that specifies a search pattern in text. These patterns are used by string-searching algorithms for find/find-replace operations on strings and for validation of input.
## Summary
This tutorial will explain basics of Regular Expression(regex) and various components used as part of regex-URL. 
* Regular expression to match a URL – /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
* Note: For more details on regex, please refer to https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
## Table of Contents

-[Basics](#Basics)

-[Anchors](#anchors)

-[Quantifiers](#quantifiers)

-[Capturing groups](#capturing-groups)

-[Character class](#character-class)

-[Meta characters](#meta-characters)

-[URL regex](#url-regex)

-[Author](#author)

## Regex Components
### Basics
* Literal Character in regex is similar to reqular search that matches literal characters. Example: \ABC - this matches string ABC
* Regex variable in Javascript is declared using forward slash /  /. Example: var x = /hello/;
### Anchors
* Anchors match just the position of character. Some of Anchors are 

| Symbol | Description |
| -------|-------------|
|^| Beginning of string| 
|$| End of string|

## Quantifiers
* Indicates number of characters that needs to be matched. Some of Quantifiers are

| Symbol | Description |
|--------|-------------|
|?| matches the expression given before ?, 0 or 1 time (optionally) |
|*| matches the expression given before *, 0 or more times |
|+| matches the expresssion given before +, 1 or more times (atleast once) |
|{min, max} | matches the expression preceeding curly brackets with the given range |

## Capturing Groups
* Matches expression and remembers the match. Entire regex is group 0 and subgroup starts with 1. 

| Symbol | Description |
|--------|-------------|
| () | matches expression within parentheses and remembers with subgroup starting with 1|

## Character Class
* Matches anything that is enclosed within square brackets. Example: l[yi]nk - would match string lynk or link.
Note: Hypen "-" is this is not first character in character class, it would consider hypen as range. Example: [-.] - matches hypen or dot. [a-z] - matches all letters.

| Symbol | Description |
|--------|-------------|
| []| matches anything that is enclosed within quare brackets|

## Meta Characters

| Symbol | Description |
|--------|-------------|
|\d| indicates numbers 0-9|
|\w| indicates alphanumberic character a-z, A-Z, 0-9
|a-z| any letters|

## URL regex 
This section explains each part of the URL regex /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
To make it simple, URL regex is grouped based on capturing group (that are enclosed within parentheses ()).

* / / - regex is enclosed within forward slash

| ^ | (https?:\\ / \\ /)? | ([\da-z\.-]+) | \. | ([a-z\.]{2,6}) | ([\/\w \.-]*)* | \/ | ? | $ |
|---|---------------------|---------------|----|----------------|----------------|----|---|---|
| Anchor:start of string| group 1 (see 👇  ) | group 2 (see 👇 ) | literal dot | group 3 (see 👇 ) | group 4 (see 👇 ) | literal / | quantifier:optionally (0 or 1) | Anchor:end of string|

* Group 1 : (https?:\\ / \\ /)? 
remembers it as "group 1" and "?" at end of group is to be matched optionally 0 or 1 time.
"http" is literal character match. "s?" matches character s optionally (0 or 1 time).
":" is lieteral colon match.
"\/" matches character / .

*  Group 2: ([\da-z\.-]+)
remembers it as "group 2".
"[\da-z\.-]+" -  "[]" represents character class and "+" at end of character class denotes that the token is matched atleast 1 to as many times as it appears.
"\d" - matches numbers 0-9.
"a-z" - matches single character in range a-z.

* Group 3: ([a-z\.]{2,6})
remembers it as "group 3".
"{2,6}" quantifier matches previous token for min of 2 to max of 6 times.
"[a-z\.]" - matches single character in range a-z for specified quantifier, followed by literal dot.

* Group 4: ([\/\w \.-]*)*
remembers it as "group 4".
"*" matches token 0 or more times
"[\/\w \.-]" - "\/" matches character /, "\w" matches any letter or number a-z,A-Z, 0-9 , "\." - literal dot and "-"hypen

## Author
Sivaranjani - a student of GA Tech learning various aspects to become a Full Stack Developer.
Here is my github link: https://github.com/Sivaparam
