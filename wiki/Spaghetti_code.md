
**Spaghetti code** is a [pejorative](pejorative "wikilink") phrase for
unstructured and
difficult-to-[maintain](Software_maintenance "wikilink") [source
code](source_code "wikilink"). Spaghetti code can be caused by several
factors, such as volatile
[project](Software_project_management "wikilink") requirements, lack of
[programming style](programming_style "wikilink") rules, and
insufficient ability or experience.

Meaning
-------

Code that overuses [GOTO](Goto "wikilink") statements rather than
[structured](Structured_programming "wikilink") programming constructs,
resulting in convoluted and unmaintainable programs, is often called
spaghetti code. Such code has a complex and tangled [control
structure](control_structure "wikilink"), resulting in a program flow
that is conceptually like a [bowl of
spaghetti](Spaghetti#Serving "wikilink"), twisted and tangled . In a
1980 publication by the [United States National Bureau of
Standards](National_Institute_of_Standards_and_Technology "wikilink"),
the phrase **spaghetti program** was used to describe older programs
having “fragmented and scattered files”. Spaghetti code can also
describe an [anti-pattern](anti-pattern "wikilink") in which
[object-oriented code](Object-oriented_programming "wikilink") is
written in a procedural style, such as by creating classes whose methods
are overly long and messy, or forsaking object oriented concepts like
[polymorphism](Polymorphism_(computer_science) "wikilink"). The
presence of this form of spaghetti code can significantly reduce the
comprehensibility of a system.

History
-------

It is not clear when the phrase spaghetti code came into common usage;
however, several references appeared in 1977 including *Macaroni is
Better Than Spaghetti* by Steele published in Proceedings of the 1977
symposium on artificial intelligence and programming languages. In the
1978 book *A primer on disciplined programming using PL/I, PL/CS, and
PL/CT*, Richard Conway used the term to describe types of programs that
“have the same clean logical structure as a plate of spaghetti”, a
phrase repeated in the 1979 book *An Introduction to Programming* he
co-authored with [David Gries](David_Gries "wikilink"). In the 1988
paper *A spiral model of software development and enhancement*, the term
is used to describe the older practice of the *code and fix model*,
which lacked planning and eventually led to the development of the
[waterfall model](waterfall_model "wikilink"). In the 1979 book
*Structured programming for the COBOL programmer*, author Paul Noll uses
the phrases *spaghetti code* and *rat's nest* as synonyms to describe
poorly structured source code.

In the *Ada – Europe '93* conference,
[Ada](Ada_(programming_language) "wikilink") was described as forcing
the programmer to “produce understandable, instead of spaghetti code”,
because of its restrictive exception propagation mechanism.

In a 1981 computer languages spoof in *The Michigan Technic* titled
“BASICally speaking...FORTRAN bytes!!”, the author described
[FORTRAN](FORTRAN "wikilink") as “proof positive that the cofounders of
[IBM](International_Business_Machines "wikilink") were Italian, for it
consists entirely of spaghetti code”.

Related phrases
---------------

### Ravioli code

[Ravioli](Ravioli "wikilink") code is a term specific to
[object-oriented programming](object-oriented_programming "wikilink").
It describes code that comprises well-structured
[classes](Class_(computer_programming) "wikilink") that are easy to
understand in isolation, but difficult to understand as a whole.

### Lasagna code

[Lasagna](Lasagna "wikilink") code refers to code whose layers are so
complicated and intertwined that making a change in one layer would
necessitate changes in all other layers.

Examples
--------

Here follows what would be considered a trivial example of spaghetti
code in [BASIC](BASIC_programming_language "wikilink"). The program
prints each of the numbers 1 to 100 to the screen along with its square.
Indentation is not used to differentiate the various actions performed
by the code, and that the program's [`GOTO`](Goto "wikilink") statements
create a reliance on [line numbers](line_number "wikilink"). The flow of
execution from one area to another is harder to predict. Real-world
occurrences of spaghetti code are more complex and can add greatly to a
program's maintenance costs.

``` {.gwbasic}
1 i=0
2 i=i+1
3 PRINT i; "squared=";i*i
4 IF i>=100 THEN GOTO 6
5 GOTO 2
6 PRINT "Program Completed."
7 END
```

Here is the same code written in a [structured
programming](structured_programming "wikilink") style:

``` {.gwbasic}
1 FOR i=1 TO 100
2     PRINT i;"squared=";i*i
3 NEXT i
4 PRINT "Program Completed."
5 END
```

The program jumps from one area to another, but this jumping is formal
and more easily predictable, because [for loops](for_loop "wikilink")
and [functions](Subroutine "wikilink") provide [flow
control](control_flow "wikilink") whereas the *goto* statement
encourages arbitrary flow control. Though this example is small, real
world programs are composed of many lines of code and are difficult to
maintain when written in a spaghetti code fashion.

Here is another example of Spaghetti code with embedded GOTO statements.
```
SCREEN 0
 INPUT "How many numbers to sort? "; T
 DIM n(T)
 FOR i = 1 TO T
   PRINT `“`NUMBER:`”`; i
   INPUT n(i)
 NEXT i
 'Calculations:
 C = T
E180:
 C = INT(C / 2)
 IF C = 0 THEN GOTO C330
 D = T - C
 E = 1
I220:
 f = E
F230:
 g = f + C
 SWAP n(f), n(g)
 f = f - C
 IF f > 0 THEN GOTO F230
 E = E + 1
 IF E > D THEN GOTO E180
GOTO I220
C330:
 PRINT `“`The`` ``sorted`` ``list`` ``is`”
 FOR i = 1 TO T
   PRINT n(i)
 NEXT i
```

See also
--------

-   [Big ball of mud](Big_ball_of_mud "wikilink"), a piece of software
    with no perceivable architecture
-   [International Obfuscated C Code
    Contest](International_Obfuscated_C_Code_Contest "wikilink"), a
    competition to produce pleasingly obscure C code
-   [Write-only language](Write-only_language "wikilink"), a language
    with such bizarre syntax that resulting code is incomprehensible

   

External links
--------------

-   [Go To Statement Considered
    Harmful](http://portal.acm.org/citation.cfm?id=362929.362947). The
    classic repudiation of spaghetti code by [Edsger
    Dijkstra](Edsger_Dijkstra "wikilink")
-   [*We don't know where to GOTO if we don't know where we've COME
    FROM* by R. Lawrence Clark from DATAMATION, December,
    1973](http://www.fortran.com/fortran/come_from.html)
-   [Refactoring Java spaghetti code into Java bento
    code](http://yost.com/computers/java/java-spaghetti/) separating out
    a bowl full of code from one class into seven classes
-   [Objects and Frameworks – Taking a Step
    Back](https://archive.is/20130201082958/http://www.remotesynthesis.com/post.cfm/Objects-and-Frameworks--Taking-a-Step-Back)
    by Brian Rinaldi
-   [Programming Pasta - Spaghetti, Lasagna, Ravioli and Macaroni
    Code](https://www.docsity.com/en/news/programming-2/programming-pasta-spaghetti-lasagna-ravioli-macaroni-code/)
-   [Pasta Theory of
    Programming](http://whatis.techtarget.com/definition/Pasta-Theory-of-Programming)
-   [Spaghetti Code: Detangling Life and Work with Programmer Wisdom
    (English Edition)](http://spaghetticodebook.com)

----

[Wikipedia](https://en.wikipedia.org/wiki/Spaghetti_code) in [Markdown](https://github.com/rognoni/markpedia) format under the [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) license
