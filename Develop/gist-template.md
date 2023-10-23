# Exploring Regular Expressions: A Breakdown of an Email Validation Regex.

I am currently learning how to write code and develop projects. for this challenge I will explain what a REGEX, or regular expression is and break down an example for learning purposes.

## Summary

The regex statement I will be breaking down is comonly used for matching an email, it looks like the following. ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$,
This statement will check the string and makes sure it follows the email format.

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
Anchors are special regex syntax usually as a caret"^", or dollar sign "$". 
The caret at the begening of the the statement matches the beggining of the text
While the dollar sign matches at the end.
These anchors represent the front and end of a regex statement, often as a method to check users input format.
In our regex statement for matching an email ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$,
both Anchors are present, the caret at the beggining and a dollar sign at the end, this represents the start and end to the statement.
### Quantifiers
Quantifiers are used in a regex to specify a number of instances of a character, group, or character class.
In our regex statement for matching an email format, there are 3 different quantifers at different spots. The first one follows[a-z0-9_\.-] with a +, which means it is going to match one or more characters in the brackets. Again following the @ we have [\da-z\.-] followed by another +, which means its going to match the brackets again.
lastly in our quantifiers we have [\da-z\.]{2,6}, which is a range quantifier, specifying that the last part must be between 2 and 6 characters from the previous brackets.
### OR Operator
An OR Operator in a regex statement checks if a given text has either one pattern or the other, but not necessarily both. For instance, in the regex pattern "apple|banana," it searches for either "apple" or "banana" in the text.
In our regex statement  it doesn't include an OR operator because it's designed to encompass the entire email validation pattern, ensuring that the text matches the complete email format, rather than looking for one part or another.
### Character Classes
Character classes, denoted by square brackets [ ] in a regular expression, allow you to define a set of characters that should match a single character at a specific position in the text. Each character within the character class represents a valid option for that position.
In our regex statement we have 3 Character classes defined.
[a-z0-9_\.-]: This character class represents the beginning of an email field. It allows for lowercase letters (a-z), numbers (0-9), underscores (_), backslashes (\), and dots (.).
[\da-z\.-]: This character class is used in the middle part of an email validation regex. It allows for digits (\d), lowercase letters (a-z), and dots (.) and hyphens (-).
[a-z\.]: This character class is used at the ending of the email validation. Its part of the top level domain(TLD) and descirbes letters (a-z) backslashes (\) and dots (.).
### Flags
A flag in a regex statement is an optional parameter that modifies how the regex engine performs its search. In our regex statement ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$, no specific flags are specified. However, some common flags in regex are:
The 'i' flag, which stands for 'case-insensitive,' allows the regex to match characters regardless of their casing, so it can match both uppercase and lowercase letters interchangeably.
The 'g' flag, which stands for 'global,' instructs the regex engine to search for all occurrences of the pattern within the input text, rather than stopping after the first match.
### Grouping and Capturing
Grouping and Capturing, in regex there are groupings created by parenthesis, these groupings are used for treating a single portion of the pattern as a single unit.
A group can have quantifiers or alternation operators, a grouping can also backreference, meaning you can reuse a matched substring later within the same regex pattern. 
When you create a group it also captures the matched text that corresponds to that group. this capture can be used afterwords for either further processing or extraction.
Each capturing group also gets assigned a number starting from 1 on the left most group.
In our regex statement ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$, we can identify three distinct groups:
The first group ([a-z0-9_\.-]+) includes a character class and a quantifier +, allowing one or more characters from the character class.
The second group ([\da-z\.-]+) is similar, containing a character class and the same quantifier, meaning it matches any number of characters from the character class.
The third group ([a-z\.]{2,6}) has a slightly different character class and a range quantifier {2,6}, specifying that it must match between 2 to 6 characters.
### Bracket Expressions
Bracket expressions, in regex are expressions using square brackets that specify a single character or collating elements for a search result.
These are more commonly used in POSIX-style regex. There are many kinds of bracket expressions, and theyre very similar to Charcter Classes, with the main difference being available features.
We used 3 Bracket Expressions in our email verification regex: [a-z0-9_\.-],[\da-z\.-], and [a-z\.].
### Greedy and Lazy Match
Greedy and Lazy match are refering to quantifiers.
A greedy search uses every position in a string and trys to match the pattern at that position, when there is no match it goes to the next position.
### Boundaries
Boundries, in regex are the markers at the beggening and at the end of a statement that represents the start and finish of a regex statement.
Like many others the regex statement for verifying email addresses uses 2 boundries, the (^) at the start, and the ($) at the end.
### Back-references
Back-references, in regular expressions are a powerful feature that enables you to reuse a matched substring later within the same regex pattern. They serve as a way to refer back to and use what you've matched earlier, enhancing the flexibility and functionality of your regex.
A good example of this is a pattern (\b\w+\b)\s+\1, First it captures a word in (\b\w+\b), then it matches spaces in \s+, then finally it backreferences the first part of (\b\w+\b) with the \1.
Here the 1 refers to the text captured in the first group, if the same word appears again in the text, the regex will find it.
Back-references can be used for more than just text, you can find repeated characters, HTML tags and even other specific patterns.
### Look-ahead and Look-behind
Lookarounds, in regex are like checkmarks that you can perform before or after the main pattern to check if certain conditions are met without that part in the match.
In regex, a lookahead (?= ...) checks if something is there, but it doesn't include that in the match.
In regex, a lookbehind (?<= ...) checks if something was there before your target, but wont include that in the match either.
Lookaroundsw help find patterns in text by allowing you to look ahead or behind your main focus without including those parts in the final result.
## Author

My name is Jacob and im currently learning in a full stack online web developemnt program, Ive learned many things over the past five months regex being one of them. my document is meant to help me understand what a regex statement is but also to allow others to learn as well. REGEX was a term that I had never heard before starting this course. The syntax seem to be very different from other subjects ive learned. But after reviewing and describing one function then it seemed to be much clearer, and im ready to learn a new one. I hope this will give insight to someone interested in learning coding and regex statements to show that its not all that hard once you breakdown 1.
