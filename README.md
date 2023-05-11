# lab-report-3
### researching find command:

1. Using the find with -name option.

This will find a file that matches up with the specified file name.

a) Using find -name to search through directories for a specific file.


```
find technical -name "rr74.txt" > justtheonetxtfile
```

Here you can see that I used the find command with the -name option to find the path to the txt file rr74.txt. Using this 
option we can find the path without knowing which specific directory the file is in, so long as we know a directory that is
containing some path to a file with that name the find command will search every possible path for it.

