# Regex Gist

Regex, which stands for regular expressions is a tool within many programming languages 
used to search strings of characters for a specific pattern within them. 
In JavaScript a regex can be created via an expression literal, e.g.
const regEx = /pattern/;
or via calling the object constructor, e.g.
const regEx = new RegExp('pattern');
In JavaScript in order to perform a regex search on a string you would use the syntax:
regEx.test('String to be searched for pattern');
where regEx equals the pattern created in the above examples and the quoted string
is the string being tested for the regex pattern.


## Summary

const regEx = /\w+@\w+\\.com/;

const matchesRegEx = regEx.test('email@yahoo.com');

In this example the regex uses character classses and quantifiers to test a string
for the patter of 'any-text-or-numbers'@'any-text-or-numbers'.com where the quoted
text is the variable pattern and @ and .com will always be the same.
In the above example matchesRegEx will evaluate to true because the sample string
matches the pattern being tested for.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors refer to special characters that match the begin and end of the
entirety of the text being examined. ^ matches the beginning and $ matches
the end. For example /^B/ will match a capital B at the beginning of the string 
but nowhere else, 'Batman' but not 'The Batman' for example, and /t$/ will match 
a t at the end of the string, so it will match 'The Dark Knight' but not 'Harvey Dent aka Two-Face'.

### Quantifiers

Quatifiers allow you to select for specific lengths of strings or for repeating characters.
\* - will match zero or more instances
\+ - will match one or more instances
? - will match zero or one instances
{min, max} - can be used in combinations, if only the first number is entered without a comma
it will only check for that spefic number of instances. If the first number is entered
with a comma it will search for at least that many instances or more and if the max
number is specified it will search for that range of whatever character or characters precedes the curly brackets.
So /o{1, 2}/ will match the o in 'son' the os in 'soon' etc.

### OR Operator

The OR operator | /x|y/ will match either x or y in this situation.

### Character Classes

Character classes will match groups or ranges of characters.
\w will match all alphanumeric characters \W will match all non-alphanumeric characters.
. will match any one character
\d for digits \D for non-digits.
So /\w{1, 2}\d/ will match any one or two alphanumerics followed by a single digit.

### Flags

Flags will change the behavior of regexes usually the regex will only search for the first instance of the pattern but adding //g to the end of one will make it continue searching for all instances.
//i will remove case sensitivity etc.

### Grouping and Capturing

You can specify ranges or groups with [] and if you use () the regex will be remembered to be used again.
For instance \[a-z\] will search for any lowercase letter \[a-d\] will search for 
a, b, c, or d. \[0-9\] is another way to specifiy digits etc. ^ used inside 
of a bracket \[^a\] will omit that character or range from the search.

### Greedy and Lazy Match

Character classes are by default a lazy match because they will only match the first 
instance of a string being searched. They can be made greedy by adding a 
//g flag or by appending an * or + to the end of them. So essentially 
greedy searches look for all instances and lazy just for the very first.

### Boundaries

Boundaries correspond to the begin or end of words within a string eg 
/\bm/ will match any ms on the beginning of words /n\b/ will match any ns on 
the end of words.

### Look-ahead and Look-behind

Look-aheads/behinds will only match a pattern if it is followed or preceded by another given pattern, respectively. 
So /Bat(?=man)/ will only match Bat if it is followed by man and 
/(?\<=Bat)man/ will only match man if is preceded by Bat.

## Author

About Me [Github Profile](https://github.com/jpmare29)
