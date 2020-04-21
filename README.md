# line-counting
Awk script to count source lines of code, comments and ratios.

# What it does
Count code, comments and computes the ratio of code to comments across a project. Works for C and C-like syntax, 
both multiline and single-line comments. 

# How to run it

  awk -f lc.awk {list of source code files}
  
