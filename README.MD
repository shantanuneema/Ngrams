# Homework 2 : N-Grams

This homework asks you to do basic textual analysis to study the
n-gramdistribution of different languages, and examine a "mystery" text to
determine what language it is in.

# Goals

In this assignment you will:
* Write functions to perform a basic n-gram analysis of texts
* Visualize the n-gram distribution of different texts
* Use this information to analyze a new text.

# Background

## N-grams

In Lecture 5, we discussed n-grams: a way of breaking up text into smaller
chunks to analyze their distribution. n-grams are defined over either words in
a sentence (so the 3-grams in "words in a sentence" are "words in a" and "in a
sentence") or over the characters in a sentence (so the 3-grams in "sentence"
are "sen" "ent" "nte" "ten" "enc" "nce"). In this homework, we will use
characters.

It is common to "pad" strings with dummy characters (e.g., `_`) to produce more
useful n-grams (to correctly capture, for example, that 's' is the most common
letter to start words through the 3-gram `__s`). The easiest way to do this is
to alter the sentence that you're building n-grams over by adding `_`s to the
beginning and end.

The interesting feature about n-grams is that different languages have different _distributions_ of n-grams. (In the simple case, the most common letter in English is `e`, but the most common letter in Spanish is `a`. The "1-grams" for English and Spanish have different distributions). This homework will build _3-gram_ distributions for texts in different languages, and you will then use this information to make inferences about a "mystery" text.

# Instructions

## 0) Set up your repository for this homework.

Click the link on Blackboard to set up a repository for homework 2, then clone it, as you did for homework 0.

The repository should contain 5 files:

1. This README
2. A starter file with some function stubs called `hw2.py`
3. A helper file called `helper.py` (this contains the same `plotHisto` function you used in HW 1)
4. 6 translations of the UN Declaration on Human Rights in different languages: `english.txt`, `spanish.txt`, `italian.txt`, `french.txt`, `german.txt`, `portuguese.txt`
5. A "mystery" file, `mystery.txt` where you are supposed to detect the language it is in.

## 1) Homework Problem 1: Creating n-grams

For problem 1, please fill in the functions `getText`, `getNgrams`, and `getDict` as described in `hw2.py` to read an input file into a list of its lines, then process those lines to construct a _dictionary_ of n-grams. (A dictionary is a built-in Python type that creates a mapping from a key -- in this case, an n-gram -- to a value -- in this case, the number of times that n-gram appears). Pay careful attention to the processing we want you to do on each line (pad it out with `_`s, make all the text lowercase) and _how_ we want you to do the processing (using `map` when called for.)

Create a new file called `problem1.py` with code to build a dictionary for a file specified on the command line, then _process_ that dictionary to print the 10 most common n-grams in the file. (You may find the following StackOverflow post helpful: https://stackoverflow.com/questions/613183/how-do-i-sort-a-dictionary-by-value). You should use the functions that you defined in `hw2.py`.

```
> python3 problem1.py english.txt
> [('the', 149), (' th', 142), (' an', 129), ('he ', 121), ('nd ', 113), ('and', 111), ('ion', 102), (' of', 93), ('of ', 89), ('tio', 88)]
```

## 2) Homework Problem 2: Visualizing n-grams

For problem 2, create a new file called `problem2.py` with code to:

1. Build a list of all the ngrams in _all 6_ language files (i.e., build dictionaries for all 6 files and create a set of all the n-grams in those files). You may find it helpful to use the python `set` data structure.
2. Create a sorted list (alphabetical order) of all the n-grams across all 6 files.
3. Plot frequency histograms for each of the 6 language files. Do this by creating a list with one entry for each n-gram (according to the order of n-grams from step 2) and putting the frequency of that n-gram in the entry (0 if the n-gram doesn't appear in a language at all). You can reuse `plotHisto` from HW1 for this step. Store the resulting histograms in corresponding PNGs (i.e., `english.txt`'s histogram will be `english.png`).

## 3) Homework Problem 3: Identifying a language

Use the code from steps 1 and 2 to help you identify the language that `mystery.txt` is in. Print the 10 most common n-grams and compare it to the results from step 1, and plot the n-gram histogram (using the same order of n-grams you built in step 2) and compare it to the histograms in step 2. Write a paragraph explaining your guess for the language of `mystery.txt` -- include any relevant information from your investigation (including a plot of the histogram).

Please put your writeup in either a pdf called `problem3.pdf` or a Word doc called `problem3.docx`.

# What you need to submit

Each of the homework problems specify what file(s) to generate and submit for
that problem.
# Submitting your code

Please tag the version of the code that you want to submit with `submission`, as you did in HW0.

Don't forget to commit the code that you want to submit *before* tagging your submission. You have to do this in two steps.