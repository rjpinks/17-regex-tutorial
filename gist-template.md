# An explanation of /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Regex searches can be very useful. They can produce searches that would not be possible using only literal searches. This idea can be very useful in developing web applications because developers can validate user input. A common use of this would be making sure a user inserted a correct information in a username, email or password.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

The following regex is a search that would match with an email address. The regex search is /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ . The regex can be broken down into many different sections such as anchors, qualifiers, flags, etc, which will be broken down in the following paragraphs of this document.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

Anchors are special characters that signifies something special about that specific search parameter. This can be found in the very beginning of the first subexpression, ^([a-z0-9_\.-]+). The ^ signifies that the first character of the string should be one of the following.

This is not the only anchor in this expression. We see it again with the $ in the following subexpression, ([a-z\.]{2,6})$ . In this case, the $ is an anchor that states the last character of the string must be one of the following characters to match.

### Quantifiers

Quantifiers are a component of regexes that sets limits to the strings that match. They are greedy by nature, which means that they will try to match as many occurences as possible unless designated otherwise. Our regex does not have any quantifiers that were designated to be lazy. To make a quantifier lazy, we would place a ? after it.

We can see our first quantifier in this subexpression, ([a-z0-9_\.-]+) . If we look at the +, we would recognize it as a quantifier. This specific quantifier states that the occurence must have one or more match for it to qualify as a valid match.

We can see the same quantifier in the next subexpression, ([\da-z\.-]+) . It means the samething in this subexpression; it must have one or more occurence in the potential match to make it valid.

Our last subexpression also has a quantifier. This one is a little bit more complicated. If we examine ([a-z\.]{2,6})$ , we can see the quantifier {2,6}. When the curly bracket quantifier is fed two numbers, it means it must match a minimum of 2 characters but a maximum of 6. In other words, after the @ symbol, the string must be 2 through six characters long.

### OR Operator

Although the OR operator is never directly used in this regex, it is used indirectly. The a-z sections of the bracket expressions could be written [a|b|c|d| etc].

### Character Classes

We witness one character class in our regex. Character classes are components that define a set of characters. We can see this in the meta character \d in the subexpression, ([\da-z\.-]+) . This is a shorthand way of writing 0-9.

### Flags

Flags are components that are placed outside of the final /. They give added functionality or can limit the search further. Our regex does not have any, but some popular ones are g, i and m.

### Grouping and Capturing

Grouping Constructs, also known as subexpressions, are components that are marked with parenthesis. We see them with ([a-z0-9_\.-]+) , ([\da-z\.-]+)  and ([a-z\.]{2,6}) . All of our subexpressions are capturing because this is the default behavior. It would be signified with a $ in the beginning of the ()s for non-capturing.

### Bracket Expressions

These are the three bracket expressions in this regex. The wrapped contents rperesents a range of characters that we want to match. They are positive character groups by default, but if we wanted them  to be negative character groups we would put a ^ at the beginning of the expression. It is important not to get confused with ^ outside of the bracket. In this case, it is a quantifier that singals it must match the first character of the string.

In the first expression, [a-z0-9_\.-] , it could be a lowercase letter a-z. It could also be any digit 0 through 9. It could be an underscore, peroid or hyphen. In this case, it is a . because the \ signifies it as a literal. The + will be discussed in quantifiers.

In the second expression, [\da-z\.-] , the \ signifies that the d is a meta character, which stands for any digit 0-9. It could be any lowercase letter a-z. It could also be a peroid. As mentioned before, the \ in front of the . signifies it as a literal. The + will once again be discussed in the quantifiers.

In the final bracket expression, [a-z\.] , the search could be any lowercase letter a-z, once again. It could also be a period.

### Greedy and Lazy Match

All of the different segments of this regex are greedy. Greedy is the default option. If a search parameter were to be made lazy, it would have a ? after the quantifier.

### Conclusion

After looking at all of the components indivisually, it might be useful to look at the regex holistically. 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

So, the / begins our regex, and the ^ says the first character of the string must match the subexpression. The quantifier at the end says it must occur one or more times. The first character can be any lowercase letter, 0-9, a period, or a hyphen.

The @ is a literal stating that after the one or more occurence of the first expression, it must be followed by a @ to be a valid match. In otherwords, ase46@, vLet_asn23@, 54nl_asS-SGt@ would all pass, but Tlka-@ would not because the first character must be lowercase. The following letters it is not necessary.

The next subexpression must also occur one or more times as indicated by the + quantifier. The meta character \d represents any digit 0-9. We see the lowercase a-z again, the period and the hyphen. sef_46@ste passes but sef_46@S does not.

We see the period literal, so that must follow. This is quite logical because our final match results should look something like user@email.com.

The final subexpression must match between 2-6 times. Not ever email address might end in .com. It could be user@email.fr. Additionally, it could be any lowercase letter or the period.

## Author

Just a guy living in rural Illinois with an interest in computers.

-[Ryan Pinkston](http://www.github.com/rjpinks54)