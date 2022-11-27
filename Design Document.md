# Rhyme and Reason Phoneme Design Document

## 1. About

### What is the application?

This application computes how much of the English language is accessible when restricted to a list of phonemes and their associated graphemes.

### Who is it for?

This is for teachers and the parents of students to evaluate the scope and sequence of reading/spelling programs

- What problem is it solving

It is very difficult to tell what words are accessible to a student who only knows a subset of the English phoneme/grapheme combinations. This makes the evaluating "best path" for a teaching sequence extremely difficult. 

It is also difficult to gauge "progress" towards literacy, assuming mastery of the phoneme/grapheme combinations they have been taught. How can you determine "coverage" of the language, and how do you define coverage? What constitutes 100% coverage? Are there different reasonbable standards?

- How will it work?

The program will compute the phonetic/graphemic composition of a master list of English words. Subsets of this master list (**Lexicons**) will be defined corresponding to different standards of "mastery" of English vocabulary (the 1000 most common words in speech, in the newspaper, in academic publishing, etc).

A subset of the possible phoneme/grapheme combinations representing the student's progress through a reading/spelling program will be used to determine which of the words in each list are accessible. The results will be returned as percentages and as word lists.

- What are the main concepts that are involved and how are they related?




## 2. User Interface

### What are the main user stories (happy flows + alternative flows)?

We see two primary user groups: the **Researcher/Developer** and the **Student/Parent**. The Researcher/Developer is someone studying or developing a reading/spelling program. The Student or Parent is someone who wants to understand how much progress they can expect at any point in a existing reading/spelling programn.

#### Researcher/Developer

Creates a scope and sequence for evaluation by inputting phoneme/grapheme combinations in the order they are taught. These combinations can be grouyped in named lessons and these lessons can be reordered

#### Parent or Student

Selects a reading/spelling program to exaluate. They can select the "coverage" metrics they care about and view the coverage as a function of time, individual lesson, or program completion. 

They can see percent of the **Lexicons**, the number of words accessible from the **Lexicons**, and lists of words coth accessible and inaccessible from the **Lexicons**,


## 3. Technical Specification

- What technical details do developlers need to know to develop the software or new feature?
- Are there new tables to add to the database? What fields?
- How will the software technically work? Are there particular algorithms or libraries that are important?
- What will be the overall design Which classes are needed? What design patterns are used to model the concepts and relationships?
- What third-party software is needed to build the software of feature?

> Can draw class diagrams or data flow diagrams here to help illustrate

## 4. Testing and Security

- Are there specific coverage goals for the unit tests?
- What kinds of tests are needed (unit, regression, end-to-end, etc)?
- What security checks need to be in place to allow the software to ship?

### New Feature Concerns
- If New Feature, are there any potential side-effects on other areas of the - application when adding this feature?
- If New Feature, how does the feature impact the security of the software Is - there a need for a security audit before the feature ships?


## 5. Deployment

- Are there any architectural or DevOps changes needed (adding an extra microservice, changes in deployment pipelines, adding secrets to services, etc)?
- Are there any migration scripts that need to be written?

### DTAP Street:

- **Develop** - local development environment (on your machine)
- **Test** - version that runs in the cloud, or a facimilie of the deployment environment
- **Acceptance** - (Sometimes called Staging) version of the application that runs in the production environment (in the cloud, for example, on the same hosts) using a copy of the production database if possible. Private instance for developers to ensure functionality before pushing to production
- **Production** - The actual production environment

## 6. Planning

- How much time will it take to develop the software or feature?
- What are the steps and how much time does each step take?
- What are the developmental milestones and in what order?
- What are the main risk factors and are there any alternative routes to take if you find out something won't work?
- What parts are absolutely required and what parts can optionally be done at a later stage? (we're defining "done")

## 7. Broader Context

What are the limitations of the current design?
What are possible extensions to think about for the future?
Any other considerations?

> Can include some "moonshot" ideas



