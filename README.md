ee205_lab4b_octocat 2
=====================

Nothing is beyond my reach

![Octocat 2](https://www2.hawaii.edu/~marknels/ee205/images/ee205_lab4b_octocat2_400.png)

| **Estimated time to complete** | 1 hour | **Prerequisites** | Lab 2d - Octocat                        |
|--------------------------------|--------|-------------------|-----------------------------------------|
| **Point Value**                |  Small | **Link**          | https://classroom.github.com/a/AXl0WN5j |

You've learned so much... let's go back and look at our old code.

The goal of this lab is to:
  1. Refactor old code
  2. Get a better handle on hexadecimal and ASCII characters

To start this lab:
  1. Accept and clone this assignment to Popoki
  2. Copy your old octocat source file here...

         $ cp ../ee205_lab2d_octocat/octocat.c ./octocat2.c

We will only grade `octocat2.c`

...with the following command:  `$ clang -o octocat2 -Wall octocat2.c`

Document the program with `$ doxygen .doxygen/Doxyfile`

Lint the program with `$ clang-tidy octocat2.c --`

The Old Octocat looked like this:

     0:--------   1:-------*   2:------*-   3:------**   4:-----*--   5:-----*-*   6:-----**-   7:-----*** 
     8:----*---   9:----*--*  10:----*-*-  11:----*-**  12:----**--  13:----**-*  14:----***-  15:----**** 
    16:---*----  17:---*---*  18:---*--*-  19:---*--**  20:---*-*--  21:---*-*-*  22:---*-**-  23:---*-*** 

The new Octocat will look like this:

    48 0x30 0 --**----  49 0x31 1 --**---*  50 0x32 2 --**--*-  51 0x33 3 --**--** 
    52 0x34 4 --**-*--  53 0x35 5 --**-*-*  54 0x36 6 --**-**-  55 0x37 7 --**-*** 
    56 0x38 8 --***---  57 0x39 9 --***--*  58 0x3a : --***-*-  59 0x3b ; --***-** 
    60 0x3c < --****--  61 0x3d = --****-*  62 0x3e > --*****-  63 0x3f ? --****** 
    64 0x40 @ -*------  65 0x41 A -*-----*  66 0x42 B -*----*-  67 0x43 C -*----** 
    68 0x44 D -*---*--  69 0x45 E -*---*-*  70 0x46 F -*---**-  71 0x47 G -*---*** 

...which has the following changes:
  - Print 4 columns instead of 8
  - Only print the first 128... numbers (down from 256)
  - Add a zero-filled hexadecimal representation of the number 
  - Add a character representation of the number (if it's printable).  If it's
    not, print a period `.`
    
### Notes
- A well architected program (like your original Octocat) should be easy to 
  modify.  If the program has structural flaws, you'll find that it takes a bit
  of surgery to accommodate these changes.  Part of this exercise is to help 
  you recognize well-architected programs and the benefits of refactoring code.
- https://en.cppreference.com/w/c/string/byte/isprint
- By convention hex digits start with `0x` ... (which is boilerplate text to 
  `printf`).
- To print a hexadecimal number use `%x` with `printf`.  To zero-fill a 
  hexadecimal number to two spaces, use `%02x`.


### Rubric
  - You must still use (at least) 2 nested loops.  They can be `for`, `while` or 
    `do-while` loops.
  - No compiler warnings
  - No documentation warnings
  - No lint warnings
  - The code must be neat, well formatted and free of "junk" code
  - The `@author` in the code you make significant changes to must be updated
  

### Git Commands
When you're ready to turn this in:

    $ git status
    $ git add .
    $ git status
    $ git commit -m "Add Hex and ASCII values"
    $ git status
    $ git push

After you've pushed your assignment, go back to Laulima and submit the lab.  You can continue to make commits until the lab's due date.


### Project Checklist
...I think you have this without a detailed checklist
  - No compilation warnings
  - Double-check the rubric / re-read the assignment
  - All work is committed and pushed to your GitHub repo
  - Submit the assignment in Laulima
