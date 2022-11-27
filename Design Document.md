# Rhyme and Reason Phoneme Design Document

# 1. About

## What is the application?

This application computes how much of the English language is accessible when restricted to a list of phonemes and their associated graphemes.

## Who is it for?

This is for teachers and the parents of students to evaluate the scope and sequence of reading/spelling programs

### What problem is it solving

It is very difficult to tell what words are accessible to a student who only knows a subset of the English Phoneme/Grapheme Combinations. This makes the evaluating "best path" for a teaching sequence extremely difficult. 

It is also difficult to gauge "progress" towards literacy, assuming mastery of the phoneme/grapheme combinations they have been taught. How can you determine "coverage" of the language, and how do you define coverage? What constitutes 100% coverage? Are there different reasonbable standards?

### How will it work?

The program will compute the phonetic/graphemic composition of a **Master Lexicon** (an exhaustive list of words in the English language). Subsets of this lexicon will be defined corresponding to different standards of "mastery" of English vocabulary (the 1000 most common words in speech, in the newspaper, in academic publishing, etc).

A subset of the possible *Phoneme/Grapheme Combinations* and *sight words* representing the student's progress through a reading/spelling Program will be used to determine which of the words in each list are accessible. The results will be returned as percentages and as word lists.

### What are the main concepts that are involved and how are they related?

* **Coverage** - how much of the language can be decoded/encoded from the Phoneme/Grapheme/Sight Words the student has learned. Can be represented as a list of words, raw number, or percentage.

* **Lexicons** - a list of words representing different subsets of the English language. Different subsets can be defined to represent "levels" of literacy, or domains of language. (i.e. - Most common in conversation, newspapers, modern fiction, academic writing, etc)

* **Sight Words** - a word that is explicitely taught to the student. This software will consider it to be known to the student but will not apply any inferences from the phonemic/graphemic content to other words in the Lexicons. (e.g. knowing **hat** and **the** doesn't mean you know **that** )

* **Phoneme/Grapheme Combinations** - these are groupings that represent a sound to "spelling" relationship. This order is important (I think)

* **Lessons** - a group of Phoneme/Grapheme Combinations and sight words expected to be taught/learned at the same time.

* **Program** - an ordered group of Lessons. *Programs* are made of ordered *Lessons*, which are unordered groups of *Phoneme/Grapheme Combinations* and *Sight Words*.


# 2. User Interface

## What are the main user stories (happy flows + alternative flows)?

We see two primary user groups: the **Researcher/Developer** and the **Evaluator**. The **Researcher/Developer** is someone studying or developing a reading/spelling program. The **Evaluator** is someone who wants to understand how much progress they can expect at any point in a existing reading/spelling programn.

### Researcher/Developer: Teacher or Researcher

Creates a scope and sequence for evaluation by inputting Phoneme/Grapheme Combinations in the order they are taught. These combinations can be grouyped in named lessons and these lessons can be reordered

### Evaluator: Parent or Student

Selects a reading/spelling program to exaluate. They can select the "coverage" metrics they care about and view the coverage as a function of time, individual lesson, or program completion. 

They can see percent of the **Lexicons**, the number of words accessible from the **Lexicons**, and lists of words coth accessible and inaccessible from the **Lexicons**,


# 3. Technical Specification

1. The software will not require SQL or other database access. 
1. The software will rely on existing text/speech processing libraries for phonetic encoding/decoding. 
    1. List some potential libraries
    1. [eng-to-ipa](https://pypi.org/project/eng-to-ipa/#description)
1. The software will maintain Lexicons as plain text files that users can edit and manage outside the software package
1. The software will maintain Program/Lesson definitions as plain text files that users can edit and manage outside the software package
1. The software will need to implement the following algorithms:
   1. Compute phonemes from a word
   2. Compute graphemes from a word


## Design Patterns - Architecture

- What classes are needed?
- Organization / relationships?


## Third-party Software

1. GUI Library
   1. [pySimpleGUI](https://pypi.org/project/PySimpleGUI/)
2. Web Library (for web deployment)
   1. [flask](https://pypi.org/project/Flask/)


### Relationship Diagrams

```mermaid
SomeClass -> AnotherClass
```


# 4. Testing and Security

## Specific coverage goals for the unit tests

1. Cover encoding/decoding on a subset of known "tricky" words

## What kinds of tests are needed (unit, regression, end-to-end, etc)?

1. No regression testing required
2. Some end-to-end/integration testing should be implemented
   1. Do the classes properly interface?
   2. How to dest this?

## What security checks need to be in place to allow the software to ship

1. Additional consideration must be given here before any web-deployment
2. No security concerns are identified for stand-alone/desktop use



# 5. Deployment

- Are there any architectural or DevOps changes needed (adding an extra microservice, changes in deployment pipelines, adding secrets to services, etc)?
- Are there any migration scripts that need to be written?

## DTAP Street:

- **Develop** - local development environment (on your machine)
- **Test** - version that runs in the cloud, or a facimilie of the deployment environment
- **Acceptance** - (Sometimes called Staging) version of the application that runs in the production environment (in the cloud, for example, on the same hosts) using a copy of the production database if possible. Private instance for developers to ensure functionality before pushing to production
- **Production** - The actual production environment

# 6. Planning

- How much time will it take to develop the software or feature?
- What are the steps and how much time does each step take?
- What are the developmental milestones and in what order?
- What are the main risk factors and are there any alternative routes to take if you find out something won't work?
- What parts are absolutely required and what parts can optionally be done at a later stage? (we're defining "done")

# 7. Broader Context

What are the limitations of the current design?
What are possible extensions to think about for the future?
Any other considerations?

> Can include some "moonshot" ideas



