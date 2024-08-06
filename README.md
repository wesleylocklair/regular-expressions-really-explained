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
- [Conclusion](#conclusion)
- [Credits and Helpful Resources](#credits-and-helpful-resources)

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
The Or operator is a great way to narrow things down as well. `|` is used as the OR operator. To make it simple, we can use this as an example: `/^abc|cba$/`. This gives us two different answers it could be. It is either `abc` or `cba`. It cannot be `bca` or something other then what is expressed. So in our example of the hex value `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. There is an OR value in the middle of it. So either if it matches the first set of parantehesis's criteria or the second. We will go over the paranthesis and grouping in a moment. The OR operator can be used in many different ways to combine groups!

### Character Classes
How are all the characters defined? It can be a little confusing so I will break it down for you. The two main type of character classes are "meta" and "literal". "Literal", you guessed it stands for LITERALLY that character. Back to the hex value example `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. You can see the slashes, then the anchors and then the character `#`. That is used as a literal character meaning the search is looking for exactly the character `#`. Another example would be `/^Hello$/` in this example the "Hello" are all literal characters and the search is looking for each one of those. Meta characters are the ranges as well as other syntax used. For instance the `[]` or the `?`. Those are not literal and mean certain things. If you're wondering how to use a meta character as a literal charater you can do so by adding a `\` in front of it. If I wrote `\?`. Instead of using the quintifier it would turn the `?` into a literal character and search for that. Here are few other character classes:
- `.` Matches any character except the newline character (\n)

- `\d` Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

- `\w` Matches any alphanumeric character from the basic Latin alphabet, including the underscore `_`. This class is equivalent to the bracket expression `[A-Za-z0-9_]`.

- `\s` Matches a single whitespace character, including tabs and line breaks


### Flags

Flags! Flags are exceptions to rules that will change your regex. They are the only thing that go on the outside of the `/`. They are seperate from the string but give more criteria for what to search. For example, the `i` flag makes your whole search case insensitive. o the regex `/^Hello$/` will also match with "hello", "heLLo", e.t.c. There are other types of flags that you can place at the end to completely redirect your search. However for the Hex Value example we do not use one. 
### Grouping and Capturing

Now how might we organize this jumble of search parameters more? Grouping is the answer to that. `()` are used to create groups. If you wanted to break things down even more and check certain parts of a search parameter you can divide them with parenthesis. In our hex value example `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` we use the paranthesis to group the string together after stating `#` is used. Anything put in paranthesis is also literal, unless stated otherwise. In the hex example, the `[]` are stating the ranges making it go from literal characters to ranges!

### Bracket Expressions

 Brackets are used to create ranges. the `[]` is referred to as bracket expressions. Inside of these brackets is when we select what kind of ranges we are looking for. For example the regex `/^[a-zA-Z0-5%]$/`. The first `a-z` means it will search for any letter lowercase `a` through `z` of the alphabet. the `A-Z` means the same thing except searching in uppercase. the `0-5` means any number 1,2,3,4, or 5 will be searched for. The `%` is a special non letter or number character that can be included. For instance if a word contains the `%` symnbol that will be selected as well. You can use all kinds of symbols you wish to search for such as `@` `#` or `*`.

### Greedy and Lazy Match

There is different types of matching. For instance there can be lots of matches to the criteria so the quintifiers were created to regulate that. The `?` is a great example of this and is used to find 0-1 matches. We use that in our hex value so we dont not pickup a string that has more the one `#` in it. This is referred to as lazy. On the other hand "greedy" is referred to when you want as many matches as possible, so for instance the `*` quintifier is a great example. It finds as many matches to the search as possible.
### Boundaries
Boundaries check for blank spaces and if a word has an insertion next to it. For instance if you're looking for a certain word and you know there is a blank space next to it you can use either `/B` or `/b`. What these do is check to see if there is a character on whatever side of the input you put it on and either create or delete a space! 
### Back-references
Back references are used to refer to previous groups! For instancem if you made a grou with certain parameters and you wanted to use it again and add to it you can use a back reference  or `/N`. The groups start at 1 and go up from there depending on how many groups that you do have! Can be very useful to repeat information. 
### Look-ahead and Look-behind
With the look ahead and look behind it checks to see past or future critiria. For instance the look ahead can be used to see if the input matches a certain criteria. If we used something like `/^(?=.$)$`. This will collect all the inputs before a `$` in whatever you are searching. Same can be used for the look behind. To grab inputs before or after certain characters.
## Conclusion
So1 after all of that information we should be able to disect our example! In our hex value example  `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. You can see the slashes showing a regex. You can see the anchors showing the string. The lazy quintifier showing for the `#` symbol. Then using brackets to create ranges of the possible color code combo. Then using and or statement for the two different types of inputs we could get! CONGRATULATIONS! Now you understand and can read regexs!

## Credits and Helpful Resources
A Youtube video breaking down regexs-
- https://www.youtube.com/watch?v=7DG3kCDx53c


MDN explaining regular expressions-
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions.


Explaining quintifiers-
- https://www.tutorialsteacher.com/regex/quantifiers


Explaining look ahead and behind-
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookahead_assertion


## Author
I am currently a student at UNCC Coding beatcamp and putting my knowledge I have learned to the test to build applications as well as create posts and repos that are helpful!
Here is a link to my github account:

https://github.com/wesleylocklair