# Fuzzy String Matching

`fuzzyMatch` calculates a score for an item (a string or an object with string-valued properties)
against a string search term. The term does not necessarily have to be a substring of the item,
but instead the score is calculated against dominant parts of the search object. For example, the
string `FuzzyStringMatching` would score highly against the term `FSM`. If you've ever used the
Go To Anything feature in Sublime Text, you'll know what I mean.

The idea is that you use this function to give a rank to each item in a searchable array, which
can then be used to find the most relevant item in the array quickly.

The algorithm is somewhat arbitrary based on the use-case against which it was originally written,
but essentially it is tailored towards matching initial characters in camelCased strings highly,
as well as consecutive substrings.
