# Titorial - Regular Expresion (Regex)

Regular Expression or (Regex) is one of the most powerful, flexible, and efficient text processing approaches. Regex has its own terminologies, conditions, and syntax; it is, in a sense, a mini programming language. Regex can be used to add, remove, isolate, and manipulate all kinds of text and data. It could be used as a simple text editor command, e.g., search and replace, or as it’s own powerful text-processing language. Because of that, Regex has so many applications in technology today, such as: Extract Useful Information With Web Crawlers, Data Scraping and Web Scraping, Data Wrangling, and machine learning — namely, natural language process and speech recognition.

Regex is not a programming language-specific application; in fact, it can be used in all programming languages today. Programming languages give support to the usage of Reges, but all the magic and strength comes from the Regex itself.

## Summary

A Regex proves useful in matching a URL in order to locate special text patterns

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
Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These patterns are used with the exec() and test() methods of RegExp , and with the match() , matchAll() , replace() , replaceAll() , search() , and split() methods of String 
### Anchors
Anchors belong to the family of regex tokens that don't match any characters, but that assert something about the string or the matching process. Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.
### Quantifiers
Quantifiers indicate numbers of characters or expressions to match.

### OR Operator
Alternation is the term in regular expression that is actually a simple “OR”.
In a regular expression it is denoted with a vertical line character |.

For instance, we need to find programming languages: HTML, PHP, Java or JavaScript.
The corresponding regexp: html|php|java(script)?.
### Character Classes
Character classes distinguish kinds of characters such as, for example, distinguishing between letters and digits.
### Patterns & Flags
Regular expressions are patterns that provide a powerful way to search and replace in text.
In JavaScript, they are available via the RegExp object, as well as being integrated in methods of strings.

Regular expressions may have flags that affect the search.

There are only 6 of them in JavaScript:

i
With this flag the search is case-insensitive: no difference between A and a (see the example below).
g
With this flag the search looks for all matches, without it – only the first match is returned.
m
Multiline mode (covered in the chapter Multiline mode of anchors ^ $, flag "m").
s
Enables “dotall” mode, that allows a dot . to match newline character \n (covered in the chapter Character classes).
u
Enables full Unicode support. The flag enables correct processing of surrogate pairs. More about that in the chapter Unicode: flag "u" and class \p{...}.
y
“Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position)

### Grouping and Capturing
A part of a pattern can be enclosed in parentheses (...). This is called a “capturing group”.

That has two effects:

It allows to get a part of the match as a separate item in the result array.
If we put a quantifier after the parentheses, it applies to the parentheses as a whole.
Examples
Let’s see how parentheses work in examples.

Example: gogogo
Without parentheses, the pattern go+ means g character, followed by o repeated one or more times. For instance, goooo or gooooooooo.

Parentheses group characters together, so (go)+ means go, gogo, gogogo and so on.
### Bracket Expressions
Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set. You can use the ^ metacharacter to negate what is between the brackets. You will often see ranges of the alphabet or all numerals.
### Greedy and Lazy Match
Quantifiers are very simple from the first sight, but in fact they can be tricky.
We should understand how the search works very well if we plan to look for something more complex than /\d+/.
Let’s take the following task as an example.

We have a text and need to replace all quotes "..." with guillemet marks: «...». They are preferred for typography in many countries.

For instance: "Hello, world" should become «Hello, world». There exist other quotes, such as „Witaj, świecie!” (Polish) or 「你好，世界」 (Chinese), but for our task let’s choose «...».

The first thing to do is to locate quoted strings, and then we can replace them.

A regular expression like /".+"/g (a quote, then something, then the other quote) may seem like a good fit, but it isn’t!
### Boundaries
A word boundary \b is a test, just like ^ and $.

When the regexp engine (program module that implements searching for regexps) comes across \b, it checks that the position in the string is a word boundary.

There are three different positions that qualify as word boundaries:

At string start, if the first string character is a word character \w.
Between two characters in the string, where one is a word character \w and the other is not.
At string end, if the last string character is a word character \w.
### Back-references
First up, how to refer to capture group portions directly in regexp definition and replacement section. You have already seen how to refer to text captured by groups with match and matchAll methods. You've also seen how to pass captured portions to a function in replace method. More directly, you can use backreference \N (within the regexp definition) and $N (replacement section), where N is the capture group you want. What's more, you can also apply quantifiers to backreferences when used in regexp definition. All the various forms is listed below:

in replacement section, use $1, $2, etc to refer to the corresponding capture group
in replacement section, use $& to refer to entire matched portion
$` gives string before the matched portion
$' gives string after the matched portion
within regexp definition, use \1, \2, etc to refer to the corresponding capture group
### Look-ahead and Look-behind
Sometimes we need to find only those matches for a pattern that are followed or preceded by another pattern.
There’s a special syntax for that, called “lookahead” and “lookbehind”, together referred to as “lookaround”.

For the start, let’s find the price from the string like 1 turkey costs 30€. That is: a number, followed by € sign.

Lookahead
The syntax is: X(?=Y), it means "look for X, but match only if followed by Y". There may be any pattern instead of X and Y.

For an integer number followed by €, the regexp will be \d+(?=€)

Lookahead allows to add a condition for “what follows”.

Lookbehind is similar, but it looks behind. That is, it allows to match a pattern only if there’s something before it.

The syntax is:

Positive lookbehind: (?<=Y)X, matches X, but only if there’s Y before it.
Negative lookbehind: (?<!Y)X, matches X, but only if there’s no Y before it.
For example, let’s change the price to US dollars. The dollar sign is usually before the number, so to look for $30 we’ll use (?<=\$)\d+ – an amount preceded by $
## Questions
  You can see more of my work on [gavriellegarcia](https://github.com/gavriellegarcia).

  If you have any additional questions send me an owl: gavrielle.garcia@hotmail.com.  
