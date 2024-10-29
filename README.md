# Build-a-Kitty-Ipsum-Translator
## Pasos
1. Abrir nuevo terrminal bash y escribir `echo hello bash`
2. `echo hello bash > stdout.txt` Imprimimos el texto hello bash en el archivo de texto stdout.txt el cual va a crear.
3. `echo hello bash >> stdout.txt` el cual vuelva a escribir la palaba debajo
**Nota:**  El operador >> redirige y añade la salida del comando anterior al archivo stdout.txt. Si el archivo no existe, lo crea; si ya existe, agrega el texto al final sin sobreescribir el contenido existente.
4. `echo hello bash > stdout.txt` escribe la palabra de nuevo borrando todo
5. `> stdout.txt` borra todo
6. `bad_command` no existe el comando 
7. `bad_command > stderr.txt` crea archivo en blanco
8. `bad_command 2> stderr.txt`
9. `echo hello bash 1> stdout.txt`
**Nota:* Con esto, si bad_command genera un error, el mensaje de error se guardará en stderr.txt en lugar de aparecer en la terminal.
10. read NAME
11. read NAME
