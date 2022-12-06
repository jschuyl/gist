# Using Regex to Find a Color

In this gist, I will describe how regular expressions, or a regex, can be used to find color within a document that uses Hex Values to incorporate color.

## Summary

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/


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

A regex is delivered to the system so long as it's wrapped in a forward slash (/). Like any coding language, regex has its own form of the user communicating with the system. Lets take a look the ones used in this regex:

### Anchors

The anchors in regex are ^ and $.

Notice that in the example regex that after the first forward slash, there is a carat (^) right before a hash symbol (#). This means that the value that we are lookng for has to start with a hash symbol. 

### Quantifiers

The quantifiers for this regex are ?, as well as {6} and {3} that are separated by [The OR Operator](#the-or-operator) (|). This means that with this expression we are looking for:
    ? - what matches the pattern zero or more times
    {6} - Matching the pattern 6 times
    | - [Or](#the-or-operator)
    {3} matching the pattern 3 times

### Grouping Constructs

A grouping construct is what is wrapped by parentheses () 

### Bracket Expressions

### Character Classes

### The OR Operator

The OR Operator in regex is represented by a vertical line (|)

### Flags

### Character Escapes

## Author

Jedediah Schuyler has been coding for 4 months, and is currently in school to code for much longer than that. If you want to see what he is currently up to, check out his [Github Here](https://github.com/jschuyl)!
