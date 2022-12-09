# Using Regex to Find a Color

In this gist, I will describe how regular expressions, or a regex, can be used to find color within a document that uses Hex Values to incorporate color.

## Summary

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

This is the regex that we will be unwrapping together. This will find a color by it's hex values. Some examples of hex values are:  
- `#ff0000` is Red ![#ff0000](https://placehold.co/15x15/ff0000/ff0000.png)  
- `#0000ff` is Blue ![#0000ff](https://placehold.co/15x15/0000ff/0000ff.png)   
- `#ffff00` is Yellow ![#ffff00](https://placehold.co/15x15/ffff00/ffff00.png) 


This group of characters that looks a bit like the aftermath of smashing a keyboard is looking for for these values. A group of letters from a to f and numbers from 0 to 9, in sets of 6 or 3, starting with `#`. 

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

Notice that in the example regex that after the first forward slash, there is a carat `^` right before a hash symbol `#`. This means that the value that we are looking for must start with a hash symbol, which is perfect since thats what the hex values that we are searching for begin with. The `#` could be swapped out with any character or string depending on what you're looking for, but keep in mind that regex searches that use this method are case-sensitive.

For every beginning there must also be an end, the same goes for a regex. The `$` anchor is similar to a mirror image of the `^` anchor but rather than searching for what follows it, the `$` searches for the string that precedes the anchor. This means that regex is searching for a value ending in whatever string the `$` immediately follows. In this case, this regex is looking for the [subexpression](#grouping-constructs) `([a-f0-9]{6}|[a-f0-9]{3})`

### Quantifiers

The quantifiers for this regex are `?`, as well as `{6}` and `{3}` that are separated by [The OR Operator](#the-or-operator) `|`. This means that with this expression we are looking for:  

- `?` - Matching the pattern zero or more times  
- `{6}` - Matching the pattern 6 times  
- `|` - [Or](#the-or-operator)  
- `{3}` Matching the pattern 3 times  

What constitutes a pattern in regex will be touched on more in [Bracket Expressions](#bracket-expressions), but for now all we need to know is this:  

We established in [anchors](#anchors) that our regex is looking to match values that begin `^` with `#` now we know we are looking for zero or more `([`pattern that starts and ends with lowercase a-f or 0-9`]` 6 times OR `[`pattern that starts and ends with lowercase a-f or 0-9`])` 3 times and our our string regex is looking to match must end `$` with one or more of these patterns.  

Even more broken down, we're looking for a pattern that ends with 3 to 6 numbers and lowercase letters, so long as they are a-f, and begins with `#`. Keep in mind that this will return every value this matches.

### Grouping Constructs

A grouping construct is what is wrapped by parentheses `()` within the example regex. There are other was of creating a grouping contruct, but this is the method that is most commonly used. Each string wrapped within the parentheses will return the exact string order, case and all. 

### Bracket Expressions

A bracket expression is the name for anything wrapped in square brackets `[]` and represent the range of what our regex is trying to match. Unlike [grouping constructs](#grouping-constructs) which search for exact matches, a bracket expression lets us be a little loose with our parameters. Bracket expressions are still case sensitive, but by putting `a-f` within the brackets `[]` we are looking for all letters in that a-f range, m-s would do the same but for m, n, o, p, q, r, s instead of a, b, c, d, e, f but will not match the capitalized versions of the characters. 

### Character Classes

Being specific in a regex can get a bit tedious, especially when you're looking for general information. Here are some ways that you can make your searches more inclusive:  

- `.` Matches all characters so long at it's not newline `\n`
- `\d` Matches all digits, essentially the same as `[0-9]`
- `\w` Matches all alphanumeric characters in lower and uppercase, including underscore `_`
- `\s` Matches all whitespace characters, including tabs and line breaks.

By capitalizing the letter that is used in a character class, you would get the opposite of your search. `\D` would be all non-digits and so forth. [Bracket expressions](#bracket-expressions) are also a form of character classes, they just have stricter parameters that you as a user set. 

### The OR Operator

The OR Operator in regex is represented by a vertical line `|`. Lets use the example `A|B`. This means that we're matching A or B but nothing else. This can apply to more than just single characters. In our breakdown example, we're looking to match two different [bracket expressions](#bracket-expressions) `[a-f0-9]{6}|[a-f0-9]{3}`, `[a-f0-9]{6}` OR `[a-f0-6]{3}`.

### Flags

Flags are another method that allow us to make our regex searches a little more inclusive. Flags are placed at the end of a regex, after the closing `/` and are the only thing that you will place outside of a regex while still being a part of the expression itself. Here are the six flags (not the theme park):  

- `g` stands for global, meaning the regex will search for all possible string matches  
- `i` removes case sensitivity for a search  
- `m` enables multiline mode, which affects your anchors to look for matches at the beginnings and ends of lines  
- `s` enables "dotall" which allows the `.` [character class](#character-classes) to include `\n`  
- `u` allows you to look to match Unicode values
- `y` enables "sticky" mode, matches exact postions in text

### Character Escapes

By now I bet tou're wondering, "Well all these tools for searching are great, but what if I'm trying to find some of the symbols that I uses to search?" Regex has tools built in just for that occasion. By adding a backslash `\` in front of the special character we can effectivley cancel it's special meaning. So if you're trying to find a `?` your regex would look like this `/?`. Another way to get around this is by including it in a [bracket expression](#bracket-expressions) as all special characters lose their special abilities within the brackets.

## Author

Jedediah Schuyler has been coding for 4 months, and is currently in school to code for much longer than that. If you want to see what he is currently up to, check out his [Github Here](https://github.com/jschuyl)!
