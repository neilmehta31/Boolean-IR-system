# Boolean-IR-system
Boolean Information Retrieval system with complex boolean queries [and, or, not,  ')' , '('  ] .

## Boolean Information Retrieval

| Name                                       |   ID Number   |
| :----------------------------------------- | :-----------: |
| [Atishay Jain](https://github.com/AtishayJain11) | 2019A7PS0106H |
| [Fenil Bardoliya](https://github.com/FB57)  | 2019A7PS0152H |
| [Neil Mehta](https://github.com/neilmehta31)        | 2019AAPS0177H |

# Problem Statement

1. This assignment is aimed at designing and developing Boolean
Information Retrieval System, i.e., to return those documents (specifically
their names from corpus/dataset given) which satisfy Boolean (AND, OR
and NOT with their combinations).
2. The Boolean Information Retrieval System should include the following
features / pre-processing steps:
  <br/>A. Stopword Removal: Remove the common stop words from the corpus.
  <br/>B. Stemming or Lemmatization: Employ either one of the techniques for
normalization.
  <br/>C. Wildcard Query Handling: Any one of the techniques among Permuterm
or K-Gram index should be used for wildcard query management. 
  <br/>D. Spelling Correction: Edit Distance Method should be employed to
correct misspelled words.

# Introduction

This report aims to analyze and explain the design choices which have been
taken while implementing the Boolean Information Retrieval System which has
been designed using the corpus of text documents as dataset by following the
format given below :

1. System Architecture
2. TestCases
3. Observations and Design Choices
4. Conclusions


# System Architecture

## Preprocessing Steps :

```
➢ Tokenization : Tokenized all the text documents from the corpus.
➢ Stopword Removal : Removed common predefined stop words as well as
single character words from the corpus.
```
## Query Processing :

```
➢ Spelling Correction : Edit distance method has been employed to correct
misspelled spellings.
➢ WildCard Query Handling : n-gram index has been used for wildcard query
management.
➢ Stemming : Employed stemming as a normalization technique.
```



# Observation and Design Choices

```
➢ Tokenization has been done using built-in nltk library functions to get
individual words from the given corpus of text documents.
```
```
➢ Stopword removal along with removing single character words is then
performed to removethe low-level information fromour text in order to give
more focus to the important information.
```
```
➢ The data structure used for storing the keywords is an inverted index /
posting list which is adatabase indexstoring a mappingfrom content, such
as words or numbers, to its locations in a document or a set of documents.
```
```
➢ Normalization techniqueshelp in reducing the numberof unique tokens present
in the text, removing the variations in a text. and also cleaning the text by 
removing redundant information.
```
```
➢ Stemming is anelementary rule-based process for removinginflationary forms 
from a given token.We have used it since itis easier to implement and faster 
to run.
```
```
➢ Edit distance has been used for spelling correction which is a way of
quantifying how dissimilar two strings are to one another by counting the
minimum number of operations required to transform one string into the other.
```
```
➢ N-gram index which refers to thesequence of n terms(or generally tokens)
from a document by moving a floating window from the begin to the end of
the document,has been used for performing wildcardsearches.
```
```
➢ While the permuterm index is simple, it can lead to a considerable blow up
from the number of rotations per term; for a dictionary of English terms, this
can represent an almost ten-fold space increase. Hence we have used
n-gram index.
```
# Conclusions

We have implemented a Boolean Information Retrieval System with the following
features :

```
➢ Tokenization
➢ Stopword Removal
➢ Normalization using stemming as a technique
➢ Wildcard query handling using n-gram indexing
➢ Spelling correction using edit distance method
```
