# eperl
A fork of embedded perl from Marginal Hacks (http://marginalhacks.com/Hacks/ePerl/)

This tool allows you to expand perl statements inside of text files. It was originally written in C by Ralf S. Engelschall. Marginal Hacks rewrote in Perl in a fraction of the space. The actual filter program is something like 80 lines, but adding compatibility and documentation puffed it up to 1400 or so - all in one script.

# Examples

ePerl reads a text file and expands any perl code it sees between some simple delimiters (<: and :> by default). Here is a simple example - see the docs for more information.
      
      Here is the start of a text file
      <: for($i=0; $i<5; $i++) { :>//
          I can count to <:=$i:>
      <: } :>//
      Here is the end.

The output will be:

      Here is the start of a text file
        I can count to 0
        I can count to 1
        I can count to 2
        I can count to 3
        I can count to 4
      Here is the end.

Not that exciting in this simple case. Here are some important points:
The perl blocks can be split up with text (such as the begin and end of the above example)
The perl blocks can contain any valid perl, such as use of perl modules, reading of files, system calls, ...

# Full and min version

There are two versions available, full and minimal.

The full version tries to remain as compatible to the C version of ePerl as possible. The minimal version is much smaller and more efficient, so if efficiency is more important than options, than go for the minimal version. (Amongst other things, the minimal version does *not* support CGI mode).

# Usage

See http://marginalhacks.com/Hacks/ePerl/Quick_Ref.html


# License

See http://marginalhacks.com/License/
