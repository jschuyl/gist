# Using Regex to Find a Color

In this gist, I will describe how regular expressions, or a regex, can be used to find color within a document that uses Hex Values to incorporate color.

## Summary

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This is the regex that we will be unwrapping together. This will find a color by it's hex values. Some examples of hex values are:  
- `#ff0000` is Red ![#ff0000](https://placehold.co/15x15/ff0000/ff0000.png)  
- `#0000ff` is Blue ![#0000ff](https://placehold.co/15x15/0000ff/0000ff.png)   
- `#ffff00` is Yellow ![#ffff00](https://placehold.co/15x15/ffff00/ffff00.png) 


This group of characters that looks like the aftermath of smashing a keyboard is looking for for these values. A group of letters from a to z and numbers from 0 to 9, in sets of 6 or 3, starting with `#`. 

Let's see how.


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

A regex is delivered to the system so long as it's wrapped in forward slashes `/`. Like any coding language, regex has its own form of the user communicating with the system. However, the best part of a regex is that it can be used within any programming language. Lets take a look the ones used in this regex:

### Anchors

The anchors in regex are `^` and `$`. These are used to specify, in this case, a specific beginning and a not necessarily specific end.

Notice that in the example regex that after the first forward slash, there is a carat `^` right before a hash symbol `#`. This means that the value that we are looking for must start with a hash symbol, which is perfect since thats what hex values that we are searching for begin with. The `#` could be swapped out with any character or string depending on what you're looking for, but keep in mind that regex searches are case-sensitive.

### Quantifiers

The quantifiers for this regex are `?`, as well as `{6}` and `{3}` that are separated by [The OR Operator](#the-or-operator) `|`. This means that with this expression we are looking for:
    `?` - what matches the pattern zero or more times
    `{6}` - Matching the pattern 6 times
    `|` - [Or](#the-or-operator)
    `{3}` matching the pattern 3 times

### Grouping Constructs

A grouping construct is what is wrapped by parentheses `()` within the regex.

### Bracket Expressions

### Character Classes

### The OR Operator

The OR Operator in regex is represented by a vertical line `|`

### Flags

### Character Escapes

## Author

Jedediah Schuyler has been coding for 4 months, and is currently in school to code for much longer than that. If you want to see what he is currently up to, check out his [Github Here](https://github.com/jschuyl)!
