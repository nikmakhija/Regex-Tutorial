# Regex-Tutorial

A regular expression is a sequence of characters that specifies a search pattern in text. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation. 

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
The carrot ^ matches any string that starts with the patern it's applied to.

let str = 'JavaScript';
console.log(/^J/.test(str));

### Quantifiers
Quantifiers indicate numbers of characters or expressions to match.

let str = 'Quantifiers';
let re = /\d{4}/;

let result = str.match(re);

console.log(result);

### OR Operator
The pipe character | separates terms contained within each group. 

a[bc] 
a(b|c)

### Character Classes
You can tell the regex engine to match only one out of several characters.

[A-Za-z_][A-Za-z_0-9]*

### Flags
An optional parameter to a regex that modifies its behavior of searching.

const re = /ab+c/i;

### Grouping and Capturing
Make it easy to extract part of the regex match.

(\d\d)\1

### Bracket Expressions
Either a matching list expression or a non-matching list expression.

'bracket'.match(/[abcd]/) // -> matches 'a'

### Greedy and Lazy Match
A greedy match means that the regex engine (the one which tries to find your pattern in the string) matches as many characters as possible. Lazy quantifier first repeats the token as few times as required, and gradually expands the match as the engine backtracks through the regex to find an overall match.

let regexp = /".+"/g;

let str = 'a "greedy" and is "lazy" is one';

alert( str.match(regexp) ); // "greedy" and "lazy"

### Boundaries
An anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.

Pattern pattern = Pattern.compile("\\s*\\b\\-?\\d+\\s*");
String plus = " 12 ";
System.out.println(""+pattern.matcher(plus).matches());

String minus = " -12 ";
System.out.println(""+pattern.matcher(minus).matches());

pattern = Pattern.compile("\\s*\\-?\\d+\\s*");
System.out.println(""+pattern.matcher(minus).matches());

### Back-references
Match the same text as previously matched by a capturing group.

 applies the regex <([A-Z][A-Z0-9]*)\b[^>]*>.*?</\1> to the string Testing <B><I>bold italic</I></B> text

### Look-ahead and Look-behind
Collectively called "Look-around" these are zero-length assertions just like the start and end of line, and start and end of word anchors.

 (?=(regex)). 
\b\w+(?<!s)\b

## Author
A short section about the author with a link to the author's GitHub profile.

var re = require('author-regex');
 
function authors(str) {
  return re().exec(str);
}
console.log(author('Nikhil Makhija <hotmail.com> (https://github.com/nikmakhija)'));


