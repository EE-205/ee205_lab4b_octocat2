ee205_lab2d_octocat
===================

Its time to write a C program on your own.

The goal of this lab is to:
  1. Use what you learned in Lab 2c
  2. Write a simple algorithm in C
  3. Remember everything you've forgotten about programming
  4. Learn to count with your tentacles

An Octocat has 8 tentacles.  One might ask how high an Octocat can count... 
and the answer is not 8.  It ends up that an Octocat is very intelligent and 
has learned to count using all of its tentacles.

0 is when all tentacles are down.  If its first tentacle is up, that's 1.  
The second tentacle is 2.  If both the first and second are up, that's 3.  
If the 3rd tentacle is up, that's 4.  Each tentacle has a value.  
When the "up" tentacles are added together, that's the number it's thinking of.

| Tentacle       | Eighth | Seventh | Sixth | Fifth | Fourth | Third | Second | First |
|----------------|:------:|:-------:|:-----:|:-----:|:------:|:-----:|:------:|:-----:|
| Additive Value |   128  |   64    |  32   |  16   |    8   |    4  |    2   |   1   |

When all 8 tentacles are up, it has counted to 255!

Your job is to count like an Octocat... and write a C program to output all 
possible tentacle positions.
````
  0:--------   1:-------*   2:------*-   3:------**   4:-----*--   5:-----*-*   6:-----**-   7:-----*** 
  8:----*---   9:----*--*  10:----*-*-  11:----*-**  12:----**--  13:----**-*  14:----***-  15:----**** 
 16:---*----  17:---*---*  18:---*--*-  19:---*--**  20:---*-*--  21:---*-*-*  22:---*-**-  23:---*-*** 
````
... your program should print all of the values in between ...
````
232:***-*--- 233:***-*--* 234:***-*-*- 235:***-*-** 236:***-**-- 237:***-**-* 238:***-***- 239:***-**** 
240:****---- 241:****---* 242:****--*- 243:****--** 244:****-*-- 245:****-*-* 246:****-**- 247:****-*** 
248:*****--- 249:*****--* 250:*****-*- 251:*****-** 252:******-- 253:******-* 254:*******- 255:******** 
````

...where a `-` is a "down" tentacle and a `*` is an "up" tentacle.  
Resize your terminal window so it's nice and wide.

## Notes
  - Here's how to print a number with 3 spaces of left-padding:  `printf( "%3d:", x );`  
  - Compile and run the program in 1 line like this:  `$ make octocat && ./octocat`
    - `make` is a tool that automates compiling complex projects.  For a 
       simple, one-file project it runs `$ cc     octocat.c   -o octocat` for you.
    - The `&&` operator is a Bash built-in command.  It runs the second command
      only if the first command was successful.  This is a good way to 
      compile-run-test efficiently.
    - You can read about it here:  
      https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Lists 
  - Open 2 terminal windows:  One to edit.  The other to compile-and-test.  
    Often, I have a 3rd open for research.
  - I'm expecting you to write your own `main()` this time.  You have several 
    examples and Google for reference.


## Rubric
  - You must use 2 nested loops.  They can be `for`, `while` or `do-while` loops.
  - You must declare a variable that the Octocat is thinking of.  
    It starts at 0 and you must increment it in a loop.
  - You must use a bitwise comparator in an `if` statement.  Here's an example:
````
if( x & 0b00100000 ) {  // The sixth tentacle
   printf( "*" );
} else {
   printf( "-" );
}
````
  - Remember printing `"\n"` will start a new line.
  - No compiler warnings.
  - The code must be neat, well formatted and free of "junk" code.

## Git Commands
To get started, accept the assignment and then clone your repo:

    $ cd src
    $ git clone <Your repo>
    $ cd <The new directory>

Do the lab.  When you're ready to turn it in:

    $ history > history 
    $ git status
    $ git add .
    $ git status
    $ git commit -m "Initial implementation of Lab 2d"
    $ git status
    $ git push

After you've pushed your assignment, go back to Laulima and submit the lab.  
You can continue to make commits until the lab's due date.
