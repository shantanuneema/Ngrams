# N-grams

This work is basic textual analysis to study the n-gram distribution of different languages to determine if a mystery text is given, it is possible to determine what language it is in.

# Goals

* Write functions to perform a basic n-gram analysis of texts
* Visualize the n-gram distribution of different texts
* Use this information to analyze a new text.

# Background

## N-grams

n-grams is a way of breaking up text into smaller chunks to analyze their distribution. n-grams are defined over either words in a sentence (so the 3-grams in "words in a sentence" are "words in a" and "in a sentence") or over the characters in a sentence (so the 3-grams in "sentence" are "sen" "ent" "nte" "ten" "enc" "nce"). In this work, we will use characters.

_3-gram_ distributions for texts in different languages are built, and then use this information to make inferences about a "mystery" text