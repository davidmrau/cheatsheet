# cheatsheet


## Bash

Read file line by line and apply command to each line.
```
cat filename | xargs -I{} command {} 
```

Go to FOLDER and execute command in FOLDER

```
cd folder && command
```

Read ```file.txt``` line by line and search for exact matches.

```
grep -w exactmatch filename
```

Get **subsequent** unique lines:

```
uniq FILE
```

Merge all files (also in subfolders) into one file

```
find . -type f | xargs cat > file
```

Remove empty lines

```
awk 'NF' filename
```

Remove leading and trailing whitespaces

```
awk '{$1=$1};1'
```

## Python

create empy 2D-list correctly.

```
[[] for i in range(N)] != [[]]*N
```
