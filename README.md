# Away with files

Files were an important abstraction to get programming started. 

However they come with several disadvantages:

1. There is a misalignment between mental concepts in programming and their representation.


Files are a serialization of actual programming concepts. 

Source code is distributed in files. 

Git is a database that can compactly represent a directory across multiple versions.

--------------------

Perspective 1.

Textual changes 

Syntactic changes

Semantic changes

Alberto
1. Conceptual view of code reviews
2. Ordering of changes
3. Specification language for code reviews

- No one knows how to do code reviews
- Code review knowledge is spread around the brains of developers
- There is no systematic/programatic way of doing code reviews
  - What would be the specification language for code reviews?
  - Senior developers can broadcast how to do them but that's not a very efficient way of communication


Methodology for understanding changes in code reviews:
?. Knowledge assumptions on the codebase
?. Incentives of the stakeholders

1. Clustering of changes
2. Re-ordering of changes

=====

Categorization of files per 'area':

            Code 

     Tests           Documentation (READMEs, Comments in code)

        Configuration (Build system, DevOps: Docker ...)

============================================

1. Help the reviewer with a guide

= Enhanced diff between ASTs instead of text 

Renaming.
   Def          ||  Uses
 Animal -> Dog  ||    Symbol 2: f(a: Animal) -> f(a: Dog)

Detect formatting changes.

Detect code moves at the syntactic level. 

Code comments.


Code simplification (linter):
 1. Looping simplification
 2. Breaking function definitions : f => g, h
 3. Reducing complexity (cyclomatic, etc)

Code optimisation:

Bug fix / New feature / Help understand the code:
  1. Right design patterns?
  2. Tail recursive methods?
  3. Methods can be replaced by library calls?

Add tests:

Configuration setup:

============================================

2. Help provide better feedback to the author
   = Allow the reviewer to group changes by 'error type' 


====

a -> b 
  to compile symbol b, I need to compile first symbol a

g : Graph Adjancency list representation:
    Name -> Repository 
    Name -> printName
    Name -> test
    printName -> test
    Repository -> printRepository
    printName -> printRepository 

Visualization:
  DFS vs BFS

  f1: DFS without node repetition:
    Name
     - Repository 
       - printRepository
     - printName
       - test

  f2: DFS with node repetition:
    Name
     - Repository 
       - printRepository
     - printName
       - test
       - printRepository
     - test

f : Graph -> List Edges 
g : List Edges -> Graph

Notes:
 - Avoid repetition is not always good

 =====


 Current:
       Def             Use
g: Name@[L8-L11] -> L13:10-15
   Name@[L8-L11] -> L17:10-15
         ....

parse: Text -> AST
semantic: AST -> Graph (Mental map of the changes) 

   a   b
    \ / 
     c
    / \
   d   e
   