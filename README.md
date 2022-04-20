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

## Testcases
```shell
$ do_quering("julius and caesar")
```
> query in process_query ['call', 'or', 'not', '(', 'julius', 'and', 'caesar', ')']
<br/>edited_query_words after edit distance:  ['call', 'or', 'not', '(', 'julius', 'and', 'caesar', ')']
<br/>query : ['call', 'or', 'not', '(', 'julius', 'and', 'caesar', ')']
<br/>call
<br/>julius
<br/>caesar
<br/>Final result :  [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
<br/>['henry-iv-part-1_TXT_FolgerShakespeare.txt', 'henry-vi-part-1_TXT_FolgerShakespeare.txt', 'henry-vi-part-2_TXT_FolgerShakespeare.txt', 'henry-iv-part-2_TXT_FolgerShakespeare.txt', 'as-you-like-it_TXT_FolgerShakespeare.txt', 'henry-vi-part-3_TXT_FolgerShakespeare.txt', 'alls-well-that-ends-well_TXT_FolgerShakespeare.txt', 'coriolanus_TXT_FolgerShakespeare.txt', 'much-ado-about-nothing_TXT_FolgerShakespeare.txt', 'the-comedy-of-errors_TXT_FolgerShakespeare.txt', 'henry-viii_TXT_FolgerShakespeare.txt', 'cymbeline_TXT_FolgerShakespeare.txt', 'king-john_TXT_FolgerShakespeare.txt', 'julius-caesar_TXT_FolgerShakespeare.txt', 'measure-for-measure_TXT_FolgerShakespeare.txt', 'lucrece_TXT_FolgerShakespeare.txt', 'loves-labors-lost_TXT_FolgerShakespeare.txt', 'king-lear_TXT_FolgerShakespeare.txt', 'macbeth_TXT_FolgerShakespeare.txt', 'the-merchant-of-venice_TXT_FolgerShakespeare.txt', 'othello_TXT_FolgerShakespeare.txt', 'a-midsummer-nights-dream_TXT_FolgerShakespeare.txt', 'richard-iii_TXT_FolgerShakespeare.txt', 'romeo-and-juliet_TXT_FolgerShakespeare.txt', 'pericles_TXT_FolgerShakespeare.txt', 'richard-ii_TXT_FolgerShakespeare.txt', 'the-phoenix-and-turtle_TXT_FolgerShakespeare.txt', 'the-taming-of-the-shrew_TXT_FolgerShakespeare.txt', 'shakespeares-sonnets_TXT_FolgerShakespeare.txt', 'the-two-gentlemen-of-verona_TXT_FolgerShakespeare.txt', 'twelfth-night_TXT_FolgerShakespeare.txt', 'the-two-noble-kinsmen_TXT_FolgerShakespeare.txt', 'timon-of-athens_TXT_FolgerShakespeare.txt', 'the-tempest_TXT_FolgerShakespeare.txt', 'the-winters-tale_TXT_FolgerShakespeare.txt', 'titus-andronicus_TXT_FolgerShakespeare.txt', 'venus-and-adonis_TXT_FolgerShakespeare.txt', 'the-merry-wives-of-windsor_TXT_FolgerShakespeare.txt', 'hamlet_TXT_FolgerShakespeare.txt', 'henry-v_TXT_FolgerShakespeare.txt', 'antony-and-cleopatra_TXT_FolgerShakespeare.txt', 'troilus-and-cressida_TXT_FolgerShakespeare.txt']

```shell
$ do_quering("call or not (julius and caesar)")
```
> query in process_query ['call', 'or', 'not', '(', 'julius', 'and', 'caesar', ')']
<br/>edited_query_words after edit distance:  ['call', 'or', 'not', '(', 'julius', 'and', 'caesar', ')']
<br/>query : ['call', 'or', 'not', '(', 'julius', 'and', 'caesar', ')']
<br/>call
<br/>julius
<br/>caesar
<br/>Final result :  [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
<br/>['henry-iv-part-1_TXT_FolgerShakespeare.txt', 'henry-vi-part-1_TXT_FolgerShakespeare.txt', 'henry-vi-part-2_TXT_FolgerShakespeare.txt', 'henry-iv-part-2_TXT_FolgerShakespeare.txt', 'as-you-like-it_TXT_FolgerShakespeare.txt', 'henry-vi-part-3_TXT_FolgerShakespeare.txt', 'alls-well-that-ends-well_TXT_FolgerShakespeare.txt', 'coriolanus_TXT_FolgerShakespeare.txt', 'much-ado-about-nothing_TXT_FolgerShakespeare.txt', 'the-comedy-of-errors_TXT_FolgerShakespeare.txt', 'henry-viii_TXT_FolgerShakespeare.txt', 'cymbeline_TXT_FolgerShakespeare.txt', 'king-john_TXT_FolgerShakespeare.txt', 'julius-caesar_TXT_FolgerShakespeare.txt', 'measure-for-measure_TXT_FolgerShakespeare.txt', 'lucrece_TXT_FolgerShakespeare.txt', 'loves-labors-lost_TXT_FolgerShakespeare.txt', 'king-lear_TXT_FolgerShakespeare.txt', 'macbeth_TXT_FolgerShakespeare.txt', 'the-merchant-of-venice_TXT_FolgerShakespeare.txt', 'othello_TXT_FolgerShakespeare.txt', 'a-midsummer-nights-dream_TXT_FolgerShakespeare.txt', 'richard-iii_TXT_FolgerShakespeare.txt', 'romeo-and-juliet_TXT_FolgerShakespeare.txt', 'pericles_TXT_FolgerShakespeare.txt', 'richard-ii_TXT_FolgerShakespeare.txt', 'the-phoenix-and-turtle_TXT_FolgerShakespeare.txt', 'the-taming-of-the-shrew_TXT_FolgerShakespeare.txt', 'shakespeares-sonnets_TXT_FolgerShakespeare.txt', 'the-two-gentlemen-of-verona_TXT_FolgerShakespeare.txt', 'twelfth-night_TXT_FolgerShakespeare.txt', 'the-two-noble-kinsmen_TXT_FolgerShakespeare.txt', 'timon-of-athens_TXT_FolgerShakespeare.txt', 'the-tempest_TXT_FolgerShakespeare.txt', 'the-winters-tale_TXT_FolgerShakespeare.txt', 'titus-andronicus_TXT_FolgerShakespeare.txt', 'venus-and-adonis_TXT_FolgerShakespeare.txt', 'the-merry-wives-of-windsor_TXT_FolgerShakespeare.txt', 'hamlet_TXT_FolgerShakespeare.txt', 'henry-v_TXT_FolgerShakespeare.txt', 'antony-and-cleopatra_TXT_FolgerShakespeare.txt', 'troilus-and-cressida_TXT_FolgerShakespeare.txt']

```shell
$ do_quering("Bru*s and calpurnia")
```
> query in process_query ['bru*s', 'and', 'calpurnia']
<br/>edited_query_words after edit distance:  ['bru*s', 'and', 'calphurnia']
<br/>query : ['bru*s', 'and', 'calphurnia']
<br/>unique available :> zeroes_and_ones for  bruises  :> [0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
<br/>unique available :> zeroes_and_ones for  brushes  :> [0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1]
<br/>unique available :> zeroes_and_ones for  brutus  :> [0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 1, 0]
<br/>unique available :> zeroes_and_ones for  brutuss  :> [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
<br/>result of OR of wildcard:  [0, 0, 1, 1, 0, 0, 0, 1, 1, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 1, 1]
<br/>calphurnia
<br/>Final result :  [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
<br/>['julius-caesar_TXT_FolgerShakespeare.txt']

```shell
$ do_quering("NOT fear AND NOT SISTER")
```
> query in process_query ['not', 'fear', 'and', 'not', 'sister']
<br/>edited_query_words after edit distance:  ['not', 'fear', 'and', 'not', 'sister']
<br/>query : ['not', 'fear', 'and', 'not', 'sister']
<br/>fear
<br/>sister
<br/>Final result :  [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
<br/>['the-phoenix-and-turtle_TXT_FolgerShakespeare.txt']
<br/>1

```shell
$ do_quering("not in")
```
> query in process_query ['not', 'in']
<br/>edited_query_words after edit distance:  ['not', 'bin']
<br/>query : ['not', 'bin']
<br/>bin
<br/>Final result :  [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
<br/>['henry-iv-part-1_TXT_FolgerShakespeare.txt', 'henry-vi-part-1_TXT_FolgerShakespeare.txt', 'henry-vi-part-2_TXT_FolgerShakespeare.txt', 'henry-iv-part-2_TXT_FolgerShakespeare.txt', 'as-you-like-it_TXT_FolgerShakespeare.txt', 'henry-vi-part-3_TXT_FolgerShakespeare.txt', 'alls-well-that-ends-well_TXT_FolgerShakespeare.txt', 'coriolanus_TXT_FolgerShakespeare.txt', 'much-ado-about-nothing_TXT_FolgerShakespeare.txt', 'the-comedy-of-errors_TXT_FolgerShakespeare.txt', 'henry-viii_TXT_FolgerShakespeare.txt', 'cymbeline_TXT_FolgerShakespeare.txt', 'king-john_TXT_FolgerShakespeare.txt', 'julius-caesar_TXT_FolgerShakespeare.txt', 'measure-for-measure_TXT_FolgerShakespeare.txt', 'lucrece_TXT_FolgerShakespeare.txt', 'loves-labors-lost_TXT_FolgerShakespeare.txt', 'macbeth_TXT_FolgerShakespeare.txt', 'the-merchant-of-venice_TXT_FolgerShakespeare.txt', 'othello_TXT_FolgerShakespeare.txt', 'a-midsummer-nights-dream_TXT_FolgerShakespeare.txt', 'richard-iii_TXT_FolgerShakespeare.txt', 'romeo-and-juliet_TXT_FolgerShakespeare.txt', 'pericles_TXT_FolgerShakespeare.txt', 'richard-ii_TXT_FolgerShakespeare.txt', 'the-phoenix-and-turtle_TXT_FolgerShakespeare.txt', 'the-taming-of-the-shrew_TXT_FolgerShakespeare.txt', 'shakespeares-sonnets_TXT_FolgerShakespeare.txt', 'the-two-gentlemen-of-verona_TXT_FolgerShakespeare.txt', 'twelfth-night_TXT_FolgerShakespeare.txt', 'the-two-noble-kinsmen_TXT_FolgerShakespeare.txt', 'timon-of-athens_TXT_FolgerShakespeare.txt', 'the-tempest_TXT_FolgerShakespeare.txt', 'the-winters-tale_TXT_FolgerShakespeare.txt', 'titus-andronicus_TXT_FolgerShakespeare.txt', 'venus-and-adonis_TXT_FolgerShakespeare.txt', 'the-merry-wives-of-windsor_TXT_FolgerShakespeare.txt', 'hamlet_TXT_FolgerShakespeare.txt', 'henry-v_TXT_FolgerShakespeare.txt', 'antony-and-cleopatra_TXT_FolgerShakespeare.txt', 'troilus-and-cressida_TXT_FolgerShakespeare.txt']
<br/>41


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
