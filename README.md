**1. The first thing you need to do is start the terminal. Do that by clicking the "hamburger" menu at the top left of the screen, going to the "terminal" section, and clicking "new terminal". Once you open a new one, type echo hello bash into the terminal and press enter.**

`echo hello bash`
Abrir nuevo terrminal bash y escribir 

------------------------------------------------------------------------------------------------------------------

**2. The command you just entered printed to the terminal. You can redirect that output to a file using >. Here’s an example: <command> > <filename>. Enter the same command but redirect the output into stdout.txt.**

`echo hello bash > stdout.txt`
Crea el archivo stdout.txt con el texto hello bash

**3. A stdout.txt file was created. You should take a look at it. Instead of printing hello bash to the terminal, it redirected the output to the file. A single > will create or overwrite the file. Use the same command with >> to append to the file.**

 `echo hello bash >> stdout.txt`

Este simbol >> reescribe abajo el texto: hello bash

**Nota:**  El operador >> redirige y añade la salida del comando anterior al archivo stdout.txt. Si el archivo no existe, lo crea; si ya existe, agrega el texto al final sin sobreescribir el contenido existente.

**4. Take a look at the file again. The output of echo hello bash was added to it. Use the command with one > again to overwrite the file.**

`echo hello bash > stdout.txt`
escribe la palabra de nuevo borrando todo

**5. Take a look at the file. It was overwritten with the output of the command. Enter `> stdout.txt` in the terminal to redirect nothing into the file. Effectively, emptying it.**

`> stdout.txt` 
borra todo

------------------------------------------------------------------------------------------------------------------

**6. Next, enter bad_command in the terminal to see what happens. You will get an error.**

bad_command 
no existe el comando 

**7. Enter the same command, but try to redirect the output to stderr.txt using >.**

bad_command > stderr.txt 
crea archivo en blanco

**8. There’s two types of output, stdout (standard out) for when a command is successful, and stderr (standard error) for when it’s not. Both of these will print to the terminal by default. bad_command was not a valid command, so it printed to stderr. You can redirect stderr with 2>. Enter the same command but redirect stderr to stderr.txt**

 bad_command 2> stderr.txt
 Esto escribe la slida del error en el arhivo stderr.txt El numero dos es el q se usa para redirigir

**9. Take a look at the stderr.txt file. The error was redirected to the file and nothing printed in the terminal. You used 2> to redirect stderr. Similarily, you can use 1> to redirect stdout. Enter echo hello bash again and use it to redirect stdout to the stdout.txt file.**

`echo hello bash 1> stdout.txt`
el 1 tb redirige pero el texto

**10. stdout and stderr are for output. stdin (standard in) is the third thing commands can use and is for getting input. The default is the keyboard. Enter read NAME in the terminal to see a command that uses stdin.**

`read NAME`
Manda a leer la variable name y pide q se llene el espacio

**11. The read command is looking at stdin for where to get input, which is pointing to the keyboard. Type your name and press enter.**

`Juan`
Se llena el espacio

**12. Use echo to print the variable you just created.**

`echo $NAME`
imprime el valor de la variable name que llenamos con juan

**13. Use echo to print the NAME variable again, but redirect the stdout to stdout.txt so it overwrites the file.**

`echo $NAME > stdout.txt`
manda el valor de la variable NAME al archivo stdout.txt

**14. Use echo and redirection to put the text freeCodeCamp in a name.txt file for some more testing. Remember that it will create the file if it doesn't exist.**

`echo freeCodeCamp > name.txt`
imprime el texto freeCodeCamp  en el archivo name.txt

**15. Just like you can redirect output, you can redirect stdin as well. Here's an example: <command> < <filename_for_stdin>. Use the read command to assign the NAME variable to the contents of name.txt by redirecting the stdin.**

`read NAME < name.txt`
imprime la variable NAME en el archivo name.txt

**16. stdin was pointing to the name.txt file this time. Use echo to print the NAME variable again.**

`echo $NAME`
impirme la variable NAME que en este caso es freeCodeCamp

**17. Now the variable is set to the content of the file, which was the input. Another way to set the stdin is by using the pipe (|). It will use the output from one command as input for another. Here's an example: <command_1> | <command_2>. This will take the stdout from command_1 and use it as the stdin for command_2. Use this method to echo your name and pipe the output into the read command which reads your name into the NAME variable.**

`echo Juan | read NAME`
Imprime la cadena "Juan" en la terminaL y toma esa salida y la asigna a la variable NAME.

**18. Use echo to print the variable again.**

`echo $NAME`
imprime la variabla name que en este caso es Juan

------------------------------------------------------------------------------------------------------------------

**19. It worked, but it doesn't look like it. When you used the pipe (|) to set the input for read, it ran the command in a subshell or subprocess. Basically, another terminal instance within the one you see. The variable was set in there and didn't affect the one you had previously set. cat is another command that takes input. Enter it in the terminal.**

`cat`

**Notas:**
**Funciones:** Visualizar el contenido de un archivo, Concatenar varios archivos, Crear un archivo rápidamente, 
**Adicionales:** -n: Numera las líneas del archivo.
-s: Suprime las líneas en blanco repetidas.
-b: Numera las líneas no vacías.

**20. cat will print the contents of a file or input to stdout. You didn't specify any input for the command. Feel free to type something and press enter. When you are done, press control+c to finish the command.**

`control`+`c`
finaliza el comando

**21. cat can take a filename as an argument. Use it again with your name.txt file as an arguement to print the contents of the file.**

`cat name.txt`
Lee lo que esta en el archivo name.txt

**22. Enter the same command but use redirection to set the stdin to name.txt**

`cat < name.txt`
**Notas:
<: Este símbolo se llama "redireccionamiento de entrada". Lo que hace es tomar el contenido del archivo a su derecha (en este caso, name.txt) y lo "alimenta" al comando que está a su izquierda (cat).

**23. Use echo to print your name and pipe the output into the cat command.**

`echo Juan | cat`
Muestra la palabra "Juan" en la pantalla dos veces. La primera vez porque echo la imprime directamente, y la segunda vez porque cat la recibe y la vuelve a imprimir.

------------------------------------------------------------------------------------------------------------------

**24. You should be starting to get the hang of how stdin, stdout, and stderr work but let's try another example with your own command. Use touch to create a file named script.sh.**

touch script.sh
crea el archivo 

**25. Give your new script executable permissions with the chmod command and the +x flag.**

`chmod +x script.sh`
da permisos

**26. This will be a very simple script with only a few commands. At the top of file, add a shebang that looks like this: #!/bin/bash.**

`#!/bin/bash`

**Notas:**
Su función principal es indicar al sistema operativo qué programa (o intérprete) debe utilizar para ejecutar el código que viene a continuación.

**27. Below the shebang, add a read command that reads input into a NAME variable.**
`read NAME`

**28. Below that, use echo to print Hello <name> using the variable.**

`echo Hello $NAME`

**29. One more thing. Add bad_command at the bottom of the file.** 

bad_command

**30. Your script takes input from stdin and will output to stdout and stderr. Run your script and don't input anything for now.**

./script.sh
Juan

**31. You input your name, and your script output the result of the two commands. Run the script again, but use a pipe to echo your name as the input.**

echo Juan | ./script.sh

**32. It didn't ask for input this time because you gave it input with the pipe. The two types of output were printed in the terminal. Run the same command but redirect stderr output to the stderr.txt**

`echo Juan | ./script.sh 2> stderr.txt`

Aqui imprime juan en la variable y el errro de bad command lo pone en el archivo stderr.txt de manera q la salida sale limpia

**33. Again, it didn't ask for input. This time it only printed your name to the terminal and not the output of bad_command. That produced an error, which you redirected to stderr.txt. Take a look at that file. You can redirect both the stderr and stdout by adding another redirection at the end like this: > <filename>. Enter the same command, redirect the stderr to the same place again, and the stdout to stdout.txt.**

`echo Juan | ./script.sh 2> stderr.txt > stdout.txt`

Aqui imprime juan en la variable y el error de bad command lo pone en el archivo stderr.txt de manera q la salida sale limpia y6 ademas envia la impresion al archivo stdout.txt


**34. It didn't ask for input and nothing was printed in the terminal that time. You redirected both outputs to files. You should take a look at them to see if they have what you expected. Run your script again, use redirection to set name.txt as the input. Don't redirect any of the output.**

./script.sh < name.txt
ejecuta el script con lña cvariable q esta en name.txt

**35. Excellent. Run the same command, but redirect the stderr to stderr.txt.**

./script.sh < name.txt 2> stderr.txt

**36. Nice job! Run it again, redirect the stderr to the same place and the stdout to stdout.txt**

./script.sh < name.txt 2> stderr.txt > stdout.txt
lo mismo con el error en el stderr.txt y la salida en stdout.txt

**37.  You have two kitty_ipsum files. Find out what's in them by printing the first one in the terminal with cat.**

`cat kitty_ipsum_1.txt`
desplega el texto del archivo

**38. It's some kitty ipsum. You may enjoy reading it 😄 Look at the second one with cat like you did this one.**

`cat kitty_ipsum_2.txt`

desplega el texto del archivo

------------------------------------------------------------------------------------------------------------------

**39. You will write a small script to translate both of them into doggy ipsum. For now, you will learn some commands to figure out how. The first one is wc. It prints some info about a file. It can take a file as an argument like the cat command. Use it to see what it shows you about your kitty_ipsum_1.txt file.**

`wc kitty_ipsum_1.txt`
wc (word count) sirve para contar el número de líneas, palabras y caracteres en un archivo. 
wc -lwmc kitty_ipsum_1.txt

**ouput:**
27  332 1744 kitty_ipsum_1.txt
Este comando mostrará todas las métricas para kitty_ipsum_1.txt: líneas, palabras, caracteres y bytes.
lineas palabras bytes nombre_archivo

**Notas:**
-l para mostrar solo el número de líneas.
-w para mostrar solo el número de palabras.
-c para mostrar solo el número de bytes.

**40. Not quite sure what all those numbers mean. Check the manual of the wc command to see if you can find out more.**

`man wc`

man -- manual de usuario
wc --  sirve para contar elementos específicos en un archivo como: Número de líneas (-l), Número de palabras (-w), Número de bytes (-c).

**41. wc stands for word count. It showed you how many lines were in the file, how many words, and how many bytes. Use the -l flag to only output how many lines are in the file. Don't do any redirecting of input or output.**

`wc -l kitty_ipsum_1.txt `
l: Número de líneas

**42. The file has 27 lines. Check how many words are in the file.**

`wc -w kitty_ipsum_1.txt`
Número de palabras (-w)

**43. 332 words are in the kitty_ipsum_1.txt file. Lastly, check how many characters it has.**

`wc -m kitty_ipsum_1.txt`
-m numero de caracteres

**44. Use the command without any flags to see if the numbers are the same.**

`wc kitty_ipsum_1.txt`
muestra todo

**45. That shows the byte count instead of the character count. Some characters must be more than one byte. Use cat to pipe the content of the file as the input of the wc command to see if the output is the same.**

`cat kitty_ipsum_1.txt | wc`

**46. It looks like the way you give input to a command may affect the output. It only printed the numbers that time and not the filename. Try using redirection as the input with the same file and command to see what that outputs.**

`wc < kitty_ipsum_1.txt`

------------------------------------------------------------------------------------------------------------------

**47. No filename again with fewer spaces that time. You may have to play with certain commands to get the output you are looking for. You are going to create a file that has some meta information about the two kitty ipsum files in it. Use echo and redirection to print ~~ kitty_ipsum_1.txt info ~~ to a file named kitty_info.txt. Make sure to place the text in quotes.**

`echo "~~ kitty_ipsum_1.txt info ~~" > kitty_info.txt`
crea el archivo kitty_info.txt e imprime ~~ kitty_ipsum_1.txt info ~~

**48. Open the file so you can keep track of what's in it. Use echo and the -e flag with the new line character (\n) to append Number of lines: to the kitty_info.txt file. Add the new line character at the beginning of the text so there's an empty line. Remember that you can append output to a file with >>.**

`echo -e "\nNumber of lines:" >> kitty_info.txt`

Este comando agrega el texto Number of lines: en una nueva línea al final del archivo kitty_info.txt.

**49. You should be able to find out how many lines are in the kitty_ipsum_1.txt file and add that number to the kitty_info.txt file. Use the cat command to pipe the content of kitty_ipsum_1.txt as input for the wc command. Use the flag for getting the number of lines from that input and append the number to the kitty_info.txt file. Tip: enter the command without appending to see if it's working first.**

`cat kitty_ipsum_1.txt | wc -l >> kitty_info.txt`

Muestra el contenido del archivo kitty_ipsum_1.txt, con | (pipe) Redirige la salida de cat hacia el siguiente comando, wc -l, el cual Cuenta el número de líneas en el contenido recibido, lo imprime,  añadiéndolo al final del archivo sin sobrescribir su contenido.

**50. Next, you want to put a word count of the file in the info. Use echo again to append Number of words: to kitty_info.txt. Put a new line in front of the text like you did for the first one.**

`echo -e "\nNumber of words:" >> kitty_info.txt`

imprime la palabra Number of words: en el archivo  kitty_info.txt

**51. Use cat and the pipe method again to append the number of words in kitty_ipsum_1.txt to kitty_info.txt.**

`cat kitty_ipsum_1.txt | wc -w >> kitty_info.txt`

imprime el numero de palabras en el archivo kitty_ipsum_1.txt

**52.  Next, you want to add the number of characters. Use the echo command with redirection to append Number of characters:, with a new line in front of it, to kitty_info.txt like you did with the other sentences.**

`echo -e "\nNumber of characters:" >> kitty_info.txt`

**53. Append the number of characters in kitty_ipsum_1.txt to kitty_info.txt. Use the redirection method as the input for the wc command this time instead of the piping method.**

`wc -m < kitty_ipsum_1.txt >> kitty_info.txt`

-------------------------------------------------------------------------------------------------------------------------

**54. grep is a command for searching for patterns in text. You can use it like this: grep '<pattern>' <filename>. Use it to search for the pattern meow in the kitty_ipsum_1.txt file.**

`grep 'meow' kitty_ipsum_1.txt`

busca todas las líneas en el archivo kitty_ipsum_1.txt que contengan la palabra "meow". 

**Notas:**

grep: Es el comando para buscar texto en archivos.

'meow': Es el término de búsqueda; en este caso, busca la palabra o cadena "meow".

kitty_ipsum_1.txt: Es el archivo donde se realiza la búsqueda.


**55. It showed you all the lines that contain meow somewhere in them, but it’s a little messy. View the manual of grep to see if you can find anything to help.**

`man grep`

tambien se puede usar : `grep --help`

**56. That's a lot of options. Use grep to search for the meow pattern in the same file, but add that --color flag to see if it's a little more helpful.**

`grep --color 'meow' kitty_ipsum_1.txt`

Colorea todas las palabras 'meow' en el texto

**57. That’s better. Add the flag to show all the line numbers with the command.**

`grep --color -n 'meow' kitty_ipsum_1.txt`
muestra la coincidencia y muestra en color y la linea donde esta ubicada la coincidencia


***58. It's showing the line number of each match it found. grep can use regular expressions, too. Enter the previous command, but change the pattern to meow[a-z]* to see all words that start with meow.**

`grep --color -n 'meow[a-z]*' kitty_ipsum_1.txt`

ver todas las palabras que empiezan por meow

**59. Looking at the output, you can see that it matched meow and meowzer, instead of just meow. Use the echo command and redirection to append the text Number of times meow or meowzer appears:, with a new line in front of it, to the kitty_info.txt file.**

 `echo -e "\nNumber of times meow or meowzer appears:" >> kitty_info.txt`
Este comando agregará al final de kitty_info.txt una línea en blanco, seguida del texto "Number of times meow or meowzer appears:".

***60. So how can you find how many times those two words appear? Use grep to find the meow[a-z]* pattern in the file again to see how many times they appear. Add the --color flag to the command.**

`grep --color 'meow[a-z]*' kitty_ipsum_1.txt`
Colorea todas las veces que hay una palabra que empieze por meow


**61. It looks like seven, but how can you get a count of that from the command line to append to the info file for the next piece of information? grep has a -c flag to give you a count. Enter the last command but use that instead of the --color flag.**

`grep -c 'meow[a-z]*' kitty_ipsum_1.txt`

**62. That gave you a count of the number lines that the pattern occurred on. Check the manual of grep to see if there's a way to find a count of all the words matched.**

`man grep`
nota: ese comando no aparece 

**63. It doesn't look like that's an option. But there is a -o flag that says it will put the matches on their own lines. Try that one with that command instead of the -c flag.**

`grep -o 'meow[a-z]*' kitty_ipsum_1.txt`

o: Solo muestra las coincidencias exactas, no la línea completa.

**64. That gave you each match on it's own line. You can use the wc command again to get a count of the lines to find out how many matches there are. Pipe the output of the last command into the wc command and use the flag for showing the line count.**

`grep -o 'meow[a-z]*' kitty_ipsum_1.txt | wc -l`

grep busca y wc (word count) cuenta las coincidencias


**65. Awesome. wc counted the lines in the output of the grep. That should be the count for how many times those words appear. Enter the same command but append the number to the kitty_info.txt file.**

`grep -o 'meow[a-z]*' kitty_ipsum_1.txt | wc -l >> kitty_info.txt`

**66. Append the text Lines that they appear on: to the kitty_info.txt file. Use the echo command with the -e flag again and put a new line in front of the text.**

`echo -e "\nLines that they appear on:" >> kitty_info.txt`
coloca una linea en kitty_info.txt


***67. There was a -n flag with grep to get line numbers. Use it to check the kitty_ipsum_1.txt file for the meow[a-z]* pattern again.**

`grep -n 'meow[a-z]*' kitty_ipsum_1.txt`

La salida mostrará el número de línea seguido del texto coincidente.

**68. Check the grep manual to see if there's a way to get just the line numbers.**

`man grep`
man grep no funciona en vsc se usa grep -help

**69. There doesn't appear to be a way to just get the line numbers. There's a sed command for replacing text that might work. First, some practice. Use cat to print the name.txt file in the terminal. It should still say freeCodeCamp.**

`cat name.txt`

ve el contenido del archivo name

--------------------------------------------------------------------------------------------------------------------------------------------

**70. sed can replace text like this: sed 's/<pattern_to_replace>/<text_to_replace_it_with>/' <filename>. By default, it won't replace the text in the file. It will output it to stdout. Use it to replace r with 2 in the name.txt file and the output prints to the terminal.**

`sed 's/r/2/' name.txt`

Esta línea de sed reemplaza la primera aparición de la letra "r" en cada línea de name.txt por el número "2".

**71. You can see that it replaced the r with a 2 in freeCodeCamp. Use it again to replace free with f233 in the same way.**

`sed 's/free/f233/' name.txt`

Esta línea reemplazará la primera aparición de la palabra "free" por "f233" en cada línea del archivo name.txt y mostrará el resultado en la salida estándar (normalmente la terminal). Si deseas que el archivo se modifique directamente, necesitarías agregar la opción -i para editar el archivo in situ, así: sed -i 's/free/f233/' name.txt.

**72. Try it again, replacing freecodecamp with f233C0d3C@mp.**

`sed 's/freecodecamp/f233C0d3C@mp/' name.txt`
Esta línea reemplaza todas las ocurrencias de la palabra "freecodecamp" por "f233C0d3C@mp" en el archivo name.txt


**73. Nothing was replaced that time. It didn't find the freecodecamp text you tried to replace because the case of a few letters didn't match. You can add regex flags after the last / in the sed argument. A g, for global, would replace all instances of a matched pattern, or an i to ignore the case of the pattern. Enter the same command but add the correct regex flag to ignore the case.**

`sed 's/freecodecamp/f233C0d3C@mp/i' name.txt`

Esta línea de código reemplaza cualquier ocurrencia de "freecodecamp" (sin importar mayúsculas o minúsculas) en el archivo name.txt por f233C0d3C@mp


**74. It worked that time since it wasn't required to match the case. As with any command, the input can be redirected. Use the same sed replacement and file but redirect the input this time.**

`sed 's/freecodecamp/f233C0d3C@mp/i' < name.txt`

Este comando muestra el resultado en la terminal sin modificar name.txt

**75. The method of input didn't affect the output. Use the cat and pipe method this time to set the input for the sed command, replacing the same text.**

cat name.txt | sed 's/freecodecamp/f233C0d3C@mp/i'
 este comando imprime el contenido de name.txt en la terminal con el texto reemplazado, pero sin modificar el archivo original. Para ver el resultado en un archivo, tendrías que redirigir la salida a un nuevo archivo o usar sed directamente en el archivo sin cat.

***76. Back to the task at hand. You want to add the line numbers asked for in the kitty_info.txt file. Use grep with the flag to show line numbers to find the meow[a-z]* pattern in the kitty_ipsum_1.txt file again.**

`grep -n 'meow[a-z]*' kitty_ipsum_1.txt`

este comando busca líneas en kitty_ipsum_1.txt que contengan "meow" seguido de cualquier combinación de letras minúsculas y muestra esas líneas con sus respectivos números


**77. You can use sed to change each line number in that output. Start by entering the last command and pipe the output into sed that replaces [0-9] with 1.**

`grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed 's/[0-9]/1/'

 este comando reemplaza el primer dígito encontrado en cada línea de la salida de grep por 1

**78. That matched the first digit it found on each line and replaced it with 1. Enter the same command but change the matching pattern to [0-9]+ to match one or more numbers.**

`grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed 's/[0-9]+/1/'`

Este comando busca líneas en kitty_ipsum_1.txt que contengan palabras que comiencen con "meow", muestra esas líneas con el número de línea, y luego reemplaza el número de línea con 1

**79. That didn't replace anything. Check the manual of sed quick to see if there's anything to help.**

`man sed`

**80. Looks like there's a lot of options with sed as well. There's a flag to use extended regular expressions. Add it to that previous command that didn't work so it recognizes the + in your pattern. The previous command was grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed 's/[0-9]+/1/'.**

grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/[0-9]+/1/' in the terminal

**81. It worked that time. It replaced all the numbers at the start with a 1. Next, you will use a capture group in the regex to capture the numbers so you can use them in the replacement area. Enter the same command but use s/([0-9]+)/\1/ with sed to capture the numbers at the start. It will replace them with themselves for now.**

grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+)/\1/'

**82. That matched all the numbers and replaced them with the same numbers. All you need to do is match everything else on each line and replace it with only the numbers. Add .* at the end of the sed matching pattern so it matches everything, captures the numbers, and replaces everything with the captured numbers.**

grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+).*/\1/'

**83. There's your list of numbers for the kitty_info.txt file. Enter the same command and append the list of numbers to it.**

grep -n 'meow[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+).*/\1/' >> kitty_info.txt

**84. Take a look at the file. Hopefully it doesn't look too messy. You can reset a lesson at any time if it doesn't look right, or if you accidentally change something in one of the other files. There's one more group of words to find info on for this file. Use grep with the --color flag to see all the words that start with cat in the same file. Use a similar pattern that you used to find words starting with meow.**

grep --color 'cat[a-z]*' kitty_ipsum_1.txt

**85. There's three variations of words starting with cat. Use echo with the -e flag to append Number of times cat, cats, or catnip appears: to the kitty_info.txt file. Put a new line at the beginning of the text like the other lines.**

echo -e "\nNumber of times cat, cats, or catnip appears:" >> kitty_info.txt

***86. You will want to find the number of times those words appear again. First, use grep with the correct flag to put all the matches of the cat[a-z]* pattern on their own line.**

grep -o 'cat[a-z]*' kitty_ipsum_1.txt

**87. Enter the same command and pipe the output into the command that outputs the count of those lines.**

grep -o 'cat[a-z]*' kitty_ipsum_1.txt | wc -l

**88. That's a count of how many times cat, cats, or catnip appears in the file. Enter the same command and append the count to the kitty_info.txt file.**

grep -o 'cat[a-z]*' kitty_ipsum_1.txt | wc -l >> kitty_info.txt

**89. Next, use echo to add the text Lines that they appear on: to the kitty_info.txt file again. Place a new line in front of the text like before.**

echo -e "\nLines that they appear on:" >> kitty_info.txt

**90. The process to add the lines to the file will be the same as you did before. Start by using grep to match the cat words in the file and showing the line numbers with the output.**

grep -n 'cat[a-z]*' kitty_ipsum_1.txt

**91. That shows you the line numbers and text. You will have to use sed again to extract only the line numbers. Pipe the output of the last command into sed to do that. As a reminder, the sed pattern was 's/([0-9]+).*/\1/'.**

grep -n 'cat[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+).*/\1/'

**92. Awesome. Enter the last command and append the line numbers to the kitty_info.txt file.**

grep -n 'cat[a-z]*' kitty_ipsum_1.txt | sed -E 's/([0-9]+).*/\1/' >> kitty_info.txt

**93. Hopefully your info file is looking good. Next, you want to do the same thing for the kitty_ipsum_2.txt file. Using echo in the terminal, append ~~ kitty_ipsum_2.txt info ~~ to the kitty_info.txt file. Put two new lines in front of the text this time.**

echo -e "\n\n~~ kitty_ipsum_2.txt info ~~" >> kitty_info.txt

**94. The first piece of info you want to know is the number of lines in the file. Use the terminal to append Number of lines: to the file with a new line in front.**

echo -e "\nNumber of lines:" >> kitty_info.txt

**95. Use cat with the pipe method to append the info to the kitty_info.txt file that it is asking for.**

cat kitty_ipsum_2.txt | wc -l >> kitty_info.txt

**96. Nice job! Next, use the terminal to append Number of words: to the kitty_info.txt file. Put a new line in front of the text again.**

echo -e "\nNumber of words:" >> kitty_info.txt

**97. Append the suggested info the kitty_info.txt file. Use redirection instead of the pipe method for the input this time.**

wc -w < kitty_ipsum_2.txt >> kitty_info.txt

**98. Next, is the character count. Append Number of characters: to the file with a new line in front of the text. Use the method you have been using.**

echo -e "\nNumber of characters:" >> kitty_info.txt

**99. Using the pipe or input redirection method, append the character count of kitty_ipsum_2.txt to the kitty_info.txt file.**

wc -m < kitty_ipsum_2.txt >> kitty_info.txt

**100. Excellent. Next, use grep to see how many variations of meow there are in kitty_ipsum_2.txt. Use the same pattern you used before and add the flag to show colors so it's easier to see.**

grep --color 'meow[a-z]*' kitty_ipsum_2.txt

**101. It's the same variations as the other file. Append Number of times meow or meowzer appears: to the kitty_info.txt file with a new line in front of it like before.**

echo -e "\nNumber of times meow or meowzer appears:" >> kitty_info.txt

**102. Use grep and wc in the terminal to append the suggested number to the kitty_info.txt file.**

grep -o 'meow[a-z]*' kitty_ipsum_2.txt | wc -l >> kitty_info.txt

**103. Next, use the terminal to append Lines that they appear on: to the kitty_info.txt file with a new line in front of the text.**

echo -e "\nLines that they appear on:" >> kitty_info.txt

**104. Use grep and sed in the terminal to append the suggested line numbers to the kitty_info.txt file.**

grep -n 'meow[a-z]*' kitty_ipsum_2.txt | sed -E 's/([0-9]+).*/\1/' >> kitty_info.txt

**105. Use grep to see how many variations of cat there are in kitty_ipsum_2.txt. Use the same pattern you used before and include the flag to show colors so it's easier to see.**

grep --color 'cat[a-z]*' kitty_ipsum_2.txt

**105. Same variations as the other kitty ipsum file. Append Number of times cat, cats, or catnip appears: to the kitty_info.txt file. Use the method you have been using.**

echo -e "\nNumber of times cat, cats, or catnip appears:" >> kitty_info.txt

**106. Use grep and wc in the terminal to append the suggested info to kitty_info.txt**

grep -o 'cat[a-z]*' kitty_ipsum_2.txt | wc -l >> kitty_info.txt

**107. One more. Append Lines that they appear on: to it like you did for the others.**

echo -e "\nLines that they appear on:" >> kitty_info.txt

**108. Use grep and sed in the terminal to append the suggested numbers to the kitty_info.txt file.**

grep -n 'cat[a-z]*' kitty_ipsum_2.txt | sed -E 's/([0-9]+).*/\1/' >> kitty_info.txt

**109. The kitty_info file is done and it has some information about the two ipsum files. Next, you will create a small script to translate both them into doggy ipsum. It will be as simple as replacing all the cat references with similar words for dogs. In the terminal, use touch to create translate.sh.**

touch translate.sh

**110. Give your new script executable permissions so you can run it in the terminal.**

chmod +x translate.sh

**111. Add a shebang to the script that uses bash like you did for the other script you made.**
#!/bin/bash

**112. The script will take a file as input that can be passed as an argument or read from stdin. Below the shebang, use cat to print the content of the first argument passed to the script.**

cat $1

**113. Run the script and use the first kitty ipsum file as an argument to see if it's working.**

./translate.sh kitty_ipsum_1.txt

**114. Try the same command using redirection to print the file.**

./translate.sh < kitty_ipsum_1.txt

**115. Looks like that is working. Try the cat and pipe method.**

cat kitty_ipsum_1.txt | ./translate.sh

**116. Using any of those three methods as input is working. Time to start replacing some of the text with doggy ipsum. In your script file, pipe the input into a sed that replaces catnip with dogchow.**

cat $1 | sed 's/catnip/dogchow/'

**117. Run the script passing the first kitty ipsum file as a argument to see if it's working.**

./translate.sh kitty_ipsum_1.txt

**118. If you look, you can find dogchow in there so it's probably working. To make sure pipe the results of that into a grep command that searches for dogchow. Output the results in color.**

./translate.sh kitty_ipsum_1.txt | grep --color 'dogchow'

**119. It's showing three places catnip was replaced with dogchow. To make sure you got them all, enter the previous command and search for catnip instead.**

./translate.sh kitty_ipsum_1.txt | grep --color 'catnip'

**120. It didn't output anything, so it must be replacing all the instances of catnip. You can replace many patterns using sed like this: sed 's/<pattern_1>/<replacement_1>/; s/<pattern_2>/<replacement_2>/'. Note that you need the semi-colon between the two replacement patterns and they both need to be wrapped in the quotes. In your script, add another pattern to the sed command that replaces cat with dog.**

cat $1 | sed 's/catnip/dogchow/; s/cat/dog/'

**121. Now, it should replace catnip with dogchow and cat with dog. Use the script to translate the first ipsum file again. Search the results with grep for any words that start with dog. Part of that search pattern should be [a-z]*. Make sure to show the results in color.**

./translate.sh kitty_ipsum_1.txt | grep --color 'dog[a-z]*'

**122. As expected, it replaced instances of cat with dog. Enter the same command, but search for anything starting with cat to make sure it replaced them all.**

./translate.sh kitty_ipsum_1.txt | grep --color 'cat[a-z]*'

**123. It didn't find any so it must be replacing them all. You added two patterns as part of the sed in your script. Add a third that replaces all meow words with woof.**

cat $1 | sed 's/catnip/dogchow/; s/cat/dog/; s/meow/woof/'

**124. Using your script, translate the first ipsum file again. Check the results with grep for words that start with dog or woof. Here's an example of the search pattern you want: grep '<dog_words>|<woof_words>'. To view "dog words", you would use dog[a-z]*. Be sure to view the result in color.**

./translate.sh kitty_ipsum_1.txt | grep --color 'dog[a-z]*|woof[a-z]*'

**125. That didn't work. Enter the same command, but add the flag to use extended regular expressions to the grep search so it recognizes the |.**

./translate.sh kitty_ipsum_1.txt | grep --color -E 'dog[a-z]*|woof[a-z]*'

**126. If you look closely, you can see that the meow part of meowzer on that one line didn't get replaced with woof. grep only matched the first instance of meow it found on that line. Add the "global" regex flag to all three patterns of the sed command in your script so it will replace all instances of any of the words.**

cat $1 | sed 's/catnip/dogchow/g; s/cat/dog/g; s/meow/woof/g'

**127. Enter the same command to translate the first ipsum file and see the matches of all words starting with dog or woof to see if that worked.**

./translate.sh kitty_ipsum_1.txt | grep --color -E 'dog[a-z]*|woof[a-z]*'

**128. 127. Enter the same command to translate the first ipsum file and see the matches of all words starting with dog or woof to see if that worked.**

cat $1 | sed -E 's/catnip/dogchow/g; s/cat/dog/g; s/meow|meowzer/woof/g'

**129. Now it should replace either of those two words with woof. Check it again with that command you entered before that searches for dog or woof words.**

./translate.sh kitty_ipsum_1.txt | grep --color -E 'dog[a-z]*|woof[a-z]*'

**130. It replaced meowzer that time. To be sure it replaced all the words in the file, enter the same command but check for meow or cat words in the same way.**

./translate.sh kitty_ipsum_1.txt | grep --color -E 'meow[a-z]*|cat[a-z]*'

**131. No results means it didn't find any matches for cat or meow words after being translated. Check the second kitty ipsum file for the same pattern to make sure it's replacing all those words.**

./translate.sh kitty_ipsum_2.txt | grep --color -E 'meow[a-z]*|cat[a-z]*'

**132. Okay, your script is finished. Translate the kitty_ipsum_1.txt file, using the filename as an argument, and put the output into a new doggy_ipsum_1.txt file.**

./translate.sh kitty_ipsum_1.txt > doggy_ipsum_1.txt

**133. Use cat to print the new file to the terminal.**

cat doggy_ipsum_1.txt

**134. It looks good 👍 diff is a command to view the difference between two files. You can use it like this: diff <file_1> <file_2>. Use it to view the difference between the kitty_ipsum_1 and doggy_ipsum_1 files.**

diff kitty_ipsum_1.txt doggy_ipsum_1.txt

**135. It may look a little cryptic, but it's showing the lines that don't match in the two files. Check the manual of diff to see if there's any way to make it prettier.**

man diff

**136. Use the flag to show the diff of the same two files in color.**

diff --color kitty_ipsum_1.txt doggy_ipsum_1.txt

**137. That's better. The red lines are lines that aren't in the second file, and the green lines are what they were replaced with. The line numbers that were changed are above each section. Translate your second kitty ipsum file and redirect the output into doggy_ipsum_2.txt.**

./translate.sh kitty_ipsum_2.txt > doggy_ipsum_2.txt

**138. View the content of your new file with cat**

cat doggy_ipsum_2.txt

**139. Lastly, view the diff of the two files in color again.**

diff --color kitty_ipsum_2.txt doggy_ipsum_2.txt

