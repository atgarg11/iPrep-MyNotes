# C++ string Reference

* substr(): Return a strings substring
```
    str = "How is life"
    str.substr(4,2) == "is" // result string starting at index 4
```
* reverse(): Reverse a container
```
    str = "this is kool"
    reverse(str.begin(), str.end()) => "look si siht"
```
* rfind(): Find in a string from back
```
    str = "How is life"
    str.rfind("life") => 7 // result. index of the found string
```
* find()
```
```

# Palindromes
Multiple ways to check palindormes
* Brute force way of checking end chars and moving to centre.
* DP approach. A string is palindrome if end chars are same and inner stirng is palindorme. 
    Need to take care of single digit string and two digit string
* Expand around centre. There two possibilities for centre
 * same char for odd lenght palindromes
 * same and next char for even length palndromes. 

## Examples 
* [647. Palindromic Substrings](https://leetcode.com/problems/palindromic-substrings/)
