# C language programming nuggets of knowledge

## Binary representation

### Number to binary string
[Read here](https://stackoverflow.com/questions/68069279/converting-int-to-binary-string-in-c)

### Include shared libraries
The `nm` command will display symbols from an object file. 

Some libraries such as C's `math.h` must be added this way.

[Read here](https://stackoverflow.com/questions/11336477/gcc-will-not-properly-include-math-h#answer-11336610)

# GCC

## `gdb` 

* Basics

  We input the binary to the gdb: `gdb a.out`. The symbols are loaded automatically. We can load other symbols with `file a.out`.

  To start the program, we use the `run` keyword.
  
* Breakpoints

  We can add breakpoints to our program with the `break` command. We can place them in different ways
  * `break main.c:17`
  * `break function_a`

* Stepping (`s` PC=PC+1; `n` dont follow JMP)

  With the program stopped, we can manipulate the flow of the program with

  * `s` makes the program go forward following call instructions.
  * `n` executes the next line without following the calls (functions)
  * `fin` executes until return
  * `continue` resumes the normal execution of the program 

* Inspect program's internal state

  With the `print` command we can show the current state of th program. 
  * `print variable`
  * `print $eax`

* Show more information (`info registers; info arg

  gdb can display a huge amount of information... just type `info` and see. Some data we can see:
  * `info args` shows the arguments of the program
  * `info registers` show the current state of the registers

[Tutorial here](https://cseweb.ucsd.edu/classes/fa09/cse141/tutorial_gcc_gdb.html#gdb)

[Continuing and stepping](https://sourceware.org/gdb/download/onlinedocs/gdb/Continuing-and-Stepping.html#Continuing-and-Stepping)
