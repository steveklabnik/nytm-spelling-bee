puzzlegen.cc is a simple program, in C++14, that generates anagram 
puzzles like those found in the New York Times Magazine, called
"Spelling Bee".  These puzzles present a circle of six letters
around a seventh, central letter, like

   M O
  P I S
   T U
 
The goal is to find common words that use only the letters in the
set, all of which use the central letter.  Words that use all the
letters score extra: one point for each lesser word, and three for
each one that uses all seven.  For example, for the letters above,
"mitosis" scores 1, "optimums" 3.  The program only emits puzzles
that that it finds have between 25 and 33 points possible, given
the words in its list.  Typically one should be satisfied with 20
points.

solve.sh is a simpler program that, given such a puzzle, lists
words found in /usr/share/dict/words that solve the puzzle. An
excerpt from its output for the puzzle above is,

  $ ./solve.sh imopstu
  ...
  optimum 
  optimums *
  osmosis 
  pimps 

with three-point words suffixed " *".  (The central letter comes first
in the command-line argument.)
