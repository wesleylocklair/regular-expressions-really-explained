# Regular Expressions Really Explained
This repo was created to breakdown and really explain regular expressions! These are also referred to as regex for future reference. Regex in their most simple form are search patterns.
Depending on the criteria you code yourself you can search for what you want! Why would we use this? Think about something as simple as google! When you are creating your account the system needs to make sure you're inputting valid information. For example Google uses a regex for your email input. This breaksdown your email to verify it is actually an email. Such as checking for an "@" symbol and a ".com"! This can be very useful for validating emails, phone numbers, searching through blocks of text and so on!

## Summary

To more easily explain regular expressions I will walk you through an example and explain in detail! In this breakdown I am going to explain a Hex Value regular expression. What this regular expression does is verify a color code. For example the hex value of hot pink is #FF69B4. However, everything explained you will be able to use in any regex that you decide to create for whatever purpose. Regex themselves look very difficult and confusing. for instance the regex we will be using looks like this `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. Pretty crazy right? In this tutorial I will breakdown everything about regex's to make it as simple as possible!

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

Regex's have lots of different components that make up the sequence and are the validators of the criteria. I will explain what each of them are so when you read a regex you can understand exactly what it is asking you and what exactly it is looking for! The regex search criteria is always surrounded in / brackets. Ex: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. See how the search criteria is in brackets? Those are made to be able to distinguish start and finish of the pattern. Next I will go over the other symbols and their meanings of the regex.
the back slashes make it as a regex patterna always wrapped in it

### Anchors

First off is anchors! Anchors are used as a start and finish of a string of characters. The `^` symbol is used as the start of a string and the `$`is used as a closer. Ex: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. Now you can see that the expression is surrounded in the slash brackets. The rest of it is enclosed within the anchor tags as well! This just shows where the string starts and where it ends. To make a more simple example `/^Hello There$/`. This simplifies it to make the string easier to follow from start to finish. There are different character types that go in between the anchor tags to search. We will go over literal and meta characters and breakdown both of those!


### Quantifiers


Quintifiers! Quintifiers are basically limiters. How often something can or should match. For example the `?` is a limiter to none or once. So in the example for the hex value `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. The `?` is saying that it can only have NONE or ONE `#` in it. There are other quintifiers used in other examples. Here is a list:

- `* `Matches the pattern zero or more times.
- `+`Matches the pattern one or more times.
- `?` Matches the pattern zero or one time.


The `{}` is used to create ranges for matches. Example:
- `{ x }` Matches the pattern exactly x number of times
- `{ x, }` Matches the pattern at least x number of times
- `{ x, y }` Matches the pattern from a minimum of x number of times to a maximum of y number of times

As you can tell these limiters can be very useful! For instance, If I am searching for a keyword that is between 8-12 characters long I can use the `{8,12}` quintifier to make my life simple! 

### OR Operator
The Or operator is a great way to narrow things down as well. `|` is used as the OR operator. To make it simple, we can use this as an example: `/^abc|cba$/`. This gives us two different answers it could be. It is either `abc` or `cba`. It cannot be `bca` or something other then what is expressed. So in our example of the hex value `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. There is an OR value in the middle of it. What that is saying is it can be either the first group. OR the second criteria group. So either if it matches the first set of parantehesis's criteria or the second. We will go over the paranthesis and grouping in a moment. 
### Character Classes
meta
literal
-d any digit 0-9
. any char
* 0 or more
### Flags

### Grouping and Capturing

Now how might we organize this jumble of search parameters more? Grouping is the answer to that. `()` are used to create groups. If you wanted to break things down even more and check certain parts of a search parameter you can divide them with parenthesis. In our hex value example `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` we use the paranthesis to group the string together after stating `#` is used. Anything put in paranthesis is also literal, unless stated otherwise. In the hex example, the `[]` are stating the ranges making it go from literal characters to ranges!

### Bracket Expressions

 Brackets are used to create ranges. the `[]` is referred to as bracket expressions. Inside of these brackets is when we select what kind of ranges we are looking for. For example the regex `/^[a-zA-Z0-5%]$/`. The first `a-z` means it will search for any letter lowercase `a` through `z` of the alphabet. the `A-Z` means the same thing except searching in uppercase. the `0-5` means any number 1,2,3,4, or 5 will be searched for. The `%` is a special non letter or number character that can be included. For instance if a word contains the `%` symnbol that will be selected as well. You can use all kinds of symbols you wish to search for such as `@` `#` or `*`.

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link t