# Rgular Expression

## Uninterpreted characters

Such as letters and digits, in a regular expression mean that they are present in the string and __must be placed in exactly the same order__.

>For example, the regular expression 'test01' will validate the 'test01', 'dktest01', and 'test0145g' strings but won't validate 'test10' or 'tste01'.

## The beginning and the end of the line

To check whether a string must be present at the beginning or the end of the line, you must use the __\^__ and __&__.

> If ^ is present at the beginning of the string, the validation will be done at the beginning of the chain.  
```
The '^test' regular expression will validate 'test' and 'test01l' but not 'dktest' or 'ttest01'

The regular expression 'test$' will validate 'test' and '01test', but not 'test01'

The regular expression '^test$' will only validate 'test'
```

## The any character regular expression

The dot(__.__) means any character.  
If you try to validate a dot in your speech, use the escape character, \\.
```
'^te.t' validates 'test' or 'tept'

'^test\.me$' only validates 'test.me'
```

## Character classes

To validate the characters, you can use character classes. A character class is eclosed in square brackets and contains all the allowed characters.

```
 '^tes[t0e]$' will only validate the three chains: 'test', 'tes0', and 'tese'.
[0-9] is equivalent to [0123456789] 
[a-z] matches all the letters, [abcdefghijklmnopqrstuvwxyz] 
[A-Z] matches all uppercase letters
[a-zA-Z] matches all the letters
\d is equivalent to [0-9] 
\w is equivalent to [a-zA-Z0-9_] 
[0-9] is equivalent to [0123456789] 
```

## Validating the number of characters

To validate a character one or more times, you must use braces '{x,y}', where x defines the minimum number of occurrences and y is the maximum number of occurrences.
```
^test{2, 3}$ only validates testt and testtt:

^tests{0,1}$ only validates test and tests 

. ^ {1} $ validates all the channels except one: the empty string

* is equivalent to {0} 
? is equivalent to {0, 1} 
+ is equivalent to {1} 
```