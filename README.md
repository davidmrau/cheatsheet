# cheatsheet


## Linux

Set reading and execution rights to user recursively for folder

```
setfacl -R -m u:username:r-x folder
```

## Bash

Read file line by line and apply command to each line.
```
cat filename | xargs -I{} command {} 
```

Go to FOLDER and execute command in folder

```
cd folder && command
```

Read ```file.txt``` line by line and search for exact matches.

```
grep -w exactmatch filename
```

Get **subsequent** unique lines:

```
uniq filename
```

Merge all files (also in subfolders) into one file

```
find . -type f | xargs cat > filename
```

Remove empty lines

```
awk 'NF' filename
```

Remove leading and trailing whitespaces

```
awk '{$1=$1};1' filename
```

Show lines that only exist in file `filename_A`:

```
comm -23 filename_A filename_B
```

first column of file

```
cut -f1 filename
```

## Python

create empy 2D-list correctly.

```
[[] for i in range(N)] != [[]]*N
```
