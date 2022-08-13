# Matching an Email - A Regex tutorial

This tutorial will go through and explain how regex runs to search a file for valid emails and cover some of the core concepts of Regex.

## Summary

We will go through the following regex snippet and explaining what each part is searching for or stands for. 
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
## Table of Contents

* [Anchors](#anchors)
* [Quantifiers](#quantifiers)
* [Grouping Constructs](#grouping-constructs)
* [Bracket Expressions](#bracket-expressions)
* [Character Classes](#character-classes)
* [Character Escapes](#character-escapes)
* [Author](#author)

## Regex Components

### Anchors

There are 2 anchors that are commonly used in Regex. They are `^` and `$`.
Anytime that you see a `^` this means the it is searching for whatever code follows it at the beginning of whatever string is entered.
The opposite of that is `$` which seaches for code at the end of whatever string is passed through.

### Quantifiers

There are many quantifiers in Regex. A quantifier specifies HOW many times a character should or may appear or sometimes specifies how parts of the string connect. The two quantifiers we have in our above example are `+` and `{2,6}` so let's talk about exactly what each one is looking for.
The `+` quantifier is one that connects parts of the string together. In our example there are 2 `+`'s that appear. In our above example it will connect the email name `+` company (gmail, yahoo, etc) `+` .com.
Our second quantifier is the `{2-6}` which in our example will search for the value of whatever proceeds it (whether that be letters or numbers) within the range we passed in. So we are looking for a string or character set of `[a-z\.]` that is between 2 and 6 characters long. 

### Grouping Constructs

We group constructs in Regex using () or parentheses. Anything that falls within a set of parentheses is considered its own group. There are 3 individual or single groups in our email example above. 
`([a-z0-9_\.-]+)` - matching users email or name
`([\da-z\.-]+)` - matching users email service
`([a-z\.]{2,6})` - matching .com of users email

### Bracket Expressions

Bracket Expressions in Email Validation Regex will look to validate characters or look for them to match. Any bracket expressions will represent a single character. The specific character is defined as whatever you search for in between those brackets (can be numbers, letters, periods, etc.) Let's take a look at our snippet above for any Bracket Expressions.
`[a-z0-9_\.-]` - Searching for a character that are lower case letters between a-z, any number between 0-9, or searching for any periods, underscores, or dashes.
`[\da-z\.-]` - `\d` this is searching for any digit (similar to how 0-9 does) followed by a-z which we know from above searches for any lower case letters where the last part `\.-` is searching for again any periods or dashes
`[a-z\.]` - searching for any letters a-z followed by a `.` which is being passed as a literal period to search for the .com

### Character Classes

Character classes are a shorthand way of searching for special classes that match special types of characters. Like we just mentioned above we have a few examples of this in our snippet. `\d` is searching for digits instead of the letter d. We use backslash to breakout of the characters normal behavior. We also use `\.` because we want to search for an actual period instead of the 'wildcard' that it sometimes represents (which means ANY input)

### Character Escapes

Character escapes we have covered already. The example we have in our Regex is `\` where we want to treat the character following the backslash as the literal thing we type vs a period sometimes representing wildcard or a `\d` representing a digit instead of a letter

## Author

Brandon Langer is a Full Stack Web Development student at the University of Minnesota coding bootcamp. He is set to graduate this fall, in September. Please head over to his GitHub profile [HERE]('https://github.com/Minotaurius') to check out some of his work! 