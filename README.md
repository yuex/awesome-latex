# Awesome LaTeX

Well, it's complicated, sort of.

To appreciate the awesomeness of LaTeX, you need to put aside a few hours to
fiddle with not only another gigantic tool and a not-so-easy-to-learn syntax
but also another no-so-well-managed software distribution system.

To save your time, you can just install `texlive` and use `homework.tex`. It's a
popular homework template at CMU introduced by the help page of [15251][]. When
you are done with your homework using the template, just run

    pdflatex homework.tex

`homework.tex` should be happy with the default packages included in texlive.
If everything goes well, a pdf file will be generated.

Alright, if you have some time or you find a cooler template on the Internet
which requires additional LaTeX packages, then be prepared to get some
frustrations. Here's the steps to make it work, probably.

First, install texlive using the package manager you hate or love or whatever
provided by your distribution or 3rd party or some guys you have no idea of but
you have to use.

    # gentoo example
    # set aside half an hour at least, it will take some time to compile
    # if you want cjk support, turn the flag on manually (disabled by default)
    emerge -av textlive

Second, try to compile the tex file and find out which package is missing

    pdflatex template.tex

Third, fortunately `tlmgr` provided by texlive is not working on gentoo so you
get the chance to do it in the traditional way, i.e., manually. Checkout the
[wikibook][]. In general you need to

    1. find and download the package source from CTAN https://www.ctan.org/
    2. unzip and compile the source. some authors provide a Makefile to easy
       this process. in that case you should thank his/her kindness

           latex packname.idx
           latex packname.dtx

    3. move generated files to their destinations according the table and their
       suffixes as described in the wikibook. generally, using a local texmf
       directory in your home directory is a good idea. create subdirectories
       as needed
    4. use `texhash` to update the package database

           texhash ~/texmf

Note the fun part is that if the package you are installing depends on other
CTAN packages, you have to resolve the dependencies yourself manually. So
please keep calm, carry on, and try hard to have some fun. Or what else you can
do?

Awesome, right? If you don't feel so, then try harder.

BTW, if you want to give it a shot, try compile `assignment.tex`.

-EOF-

[15251]: http://www.cs.cmu.edu/afs/cs/academic/class/15251/Site/current/Help/late
[wikibook]: https://en.wikibooks.org/wiki/LaTeX/Installing_Extra_Packages
