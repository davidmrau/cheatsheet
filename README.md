# cheatsheet


## Bash

Read ```file.txt``` and apply command to each line.
```
cat file.txt | xargs -I{} command {} 
```

Go to FOLDER and execute command in FOLDER

```
cd FOLDER && command
```
