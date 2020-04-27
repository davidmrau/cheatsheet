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

Get **subsequent** unique lines:

```
uniq FILE
```

Merge all files (also in subfolders) into one file

```
find . -type f | xargs cat > file
```

## Python

create empy 2D-list correctly.

```
[[] for i in range(N)] != [[]]*N
```
