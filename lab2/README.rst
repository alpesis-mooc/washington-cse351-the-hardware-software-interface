##############################################################################
Lab 2
##############################################################################

Prequisites

::

    $ wget https://courses.cs.washington.edu/courses/cse351/17sp/labs/lab2/<username>/lab2-bomb.tar
    $ tar xvf lab2-bomb.tar
    $ ./bomb defuser.txt


Preparations

::

    $ gdb                     # debugger
    $ objdump -t              # print out symbol table
    $ objdump -d              # dumps the assembly code of the program
    $ strings                 # prints out all printable strings 


::

    $ strings bomb > bomb-strings
    $ objdump -d bomb > bomb-assembly

phase 1

::

    $ gdb bomb
    $ break phase_1
    $ run
    $ p/x $eax             # check the variable address
    $ x /25c <address>     # check the value of the address
    $ x /100c 0x401b18     # Speedy thing goes in, speedy thing comes out.

phase 2

::

    $ break phase_2
    $ run defuser.txt
    $ disas
    $ until *<address>     # cmp address
    $ i r                  # show the content of register
    $ x/d <address>
