1. The first thing you need to do is start the terminal. Do that by clicking the "hamburger" menu at the top left of the screen, going to the "terminal" section, and clicking "new terminal". Once you open a new one, type echo hello bash into the terminal and press enter.  
     
2. The command you just entered printed to the terminal. You can redirect that output to a file using \>. Here’s an example: \<command\> \> \<filename\>. Enter the same command but redirect the output into stdout.txt.  
     
3. A stdout.txt file was created. You should take a look at it. Instead of printing hello bash to the terminal, it redirected the output to the file. A single \> will create or overwrite the file. Use the same command with \>\> to append to the file.  
     
4. Take a look at the file again. The output of echo hello bash was added to it. Use the command with one \> again to overwrite the file.  
     
5. Take a look at the file. It was overwritten with the output of the command. Enter \> stdout.txt in the terminal to redirect nothing into the file. Effectively, emptying it.  
     
6. Next, enter bad\_command in the terminal to see what happens. You will get an error.  
     
7. Enter the same command, but try to redirect the output to stderr.txt using \>.  
     
8. There’s two types of output, stdout (standard out) for when a command is successful, and stderr (standard error) for when it’s not. Both of these will print to the terminal by default. bad\_command was not a valid command, so it printed to stderr. You can redirect stderr with 2\>. Enter the same command but redirect stderr to stderr.txt  
     
9. Take a look at the stderr.txt file. The error was redirected to the file and nothing printed in the terminal. You used 2\> to redirect stderr. Similarily, you can use 1\> to redirect stdout. Enter echo hello bash again and use it to redirect stdout to the stdout.txt file.  
     
10. stdout and stderr are for output. stdin (standard in) is the third thing commands can use and is for getting input. The default is the keyboard. Enter read NAME in the terminal to see a command that uses stdin.  
      
11. The read command is looking at stdin for where to get input, which is pointing to the keyboard. Type your name and press enter.  
      
12. Use echo to print the variable you just created.

