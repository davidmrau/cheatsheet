# cheatsheet


## Linux

Set reading and execution rights to user recursively for folder

```
setfacl -R -m u:username:r-x folder
```

Convert text document to utf-8

```
vim --clean -E -s -c 'argdo set fileencoding=utf-8 nobomb | update' -c q -- file_name
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


Dowload file (FILEID) from google drive to FILENAME


```
fileId=FILEID
fileName=FILENAME
curl -sc cookie "https://drive.google.com/uc?export=download&id=${fileId}" > /dev/null
code="$(awk '/_warning_/ {print $NF}' cookie)"
curl -Lb cookie "https://drive.google.com/uc?export=download&confirm=${code}&id=${fileId}" -o ${fileN
ame}
```

Get random lines in sequence from file with probability p
```
perl -ne 'print if (rand() < p)' file.csv
```

find each line of file1 in first column of file2
```
awk 'NR == FNR { line[$0]; next } $1 in line { print $0 }' file1 file2
```


calculate average per over lines

```
awk '{x+=$0}END{print x/NR}' FILENAME
```

count number of CHAR


```
awk -F\CHAR '{print NF-1}'
```


Print column 5 of tab separated file

```
awk 'BEGIN{ FS=OFS="\t" }{ print $5 }' FILE
```


## Python

create empy 2D-list correctly.

```
[[] for i in range(N)] != [[]]*N
```

access None in tuple does not return None

```
>>> a
(1, 2, None)
>>> a[2]
>>>
```

# PyPlot

## legend to separate file

```
fig,ax = plt.subplots()
label_params = ax.get_legend_handles_labels() 
plt.tight_layout() 
    
plt.savefig(f'without_legend.pdf')
figl, axl = plt.subplots(figsize=(3,2.4))
axl.axis(False)
axl.legend(*label_params, loc='center left')
plt.tight_layout() 
plt.savefig(f'first_last.pdf')
```
