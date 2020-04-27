# cheatsheet


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


lines that are `filename_A` but not in `filename_B`

```
awk 'NR==FNR{a[$0];next} !($0 in a)' filename_A filename_B
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
