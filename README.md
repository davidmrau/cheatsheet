# cheatsheet


## Bash

Read ```file.txt``` line by line and apply command to each line.
```
cat file.txt | xargs -I{} command {} 
```

Go to FOLDER and execute command in FOLDER

```
cd FOLDER && command
```

Read ```file.txt``` line by line and search for exact matches.

```
grep -w EXACTMATCH FILE
```
