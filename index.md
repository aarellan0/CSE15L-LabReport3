# Lab Report 3 - Researching Commands
## Aaron Arellano

In this third lab report, I chose to research the grep command, which is utilized for finding specific files in directories given certain specifications.

# Alternate command 1: grep - n

One way to use the grep command would be the -n command. What this does is it prints the line number that a matching pattern is found, along with the 
contents of that line afterwards. For these next examples, findResults.txt is a file that contains the contents of the command

```
find ".txt" written_2/
```

which contains all the .txt files within the written_2 directory, with each file name being on its own seperate line.

## Grep -n example 1

In the command line, we write the following line and get the output.

```
grep -n "Bahamas" findResults.txt
173:written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
204:written_2/travel_guides/berlitz2/Bahamas-Intro.txt
206:written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
234:written_2/travel_guides/berlitz2/Bahamas-History.txt
```

With the initial command, we are intending on finding the files that contain the phrase "Bahamas" in their name. The result from the grep -n shows us 
which files within findResults.txt have the name Bahamas, but additionally also shows us which line within the file findResults.txt contains the file 
name with the given string input. 

## Grep -n example 2

In the second example, we use the following command and get the following,

```
grep -n "ch2" findResults.txt
5:written_2/non-fiction/OUP/Berk/ch2.txt
10:written_2/non-fiction/OUP/Abernathy/ch2.txt
20:written_2/non-fiction/OUP/Rybczynski/ch2.txt
34:written_2/non-fiction/OUP/Fletcher/ch2.txt
```

With this command, we are trying to find all the file names that contain "ch2" or chapter 2 in their name. The result from this specific grep-n command
shows us that in the findResults file (which contains all .txt files in written_2 repository), there are 4 files with "ch2" in their name, each from 
different authors. Again, it also shows us the specific line in the findResults.file in which these files are located in. In the end, the -n command is
useful for helping us locate where specifically certain things are within files. This can be useful for researching and citation specific quotes, 
helping us find needed information in long files without long searching and much more. The grep-n helps deliver specific locations more efficiently and 
rapidly.

# Alternate command 2: grep - A n

Another variation of the grep command is grep -A n, where n is the number of lines after the searched result line. In other words, after the grep command
finds the specific line containing the pattern, the -A n command prints the next n lines that come after the result line that we were looking for. In the
following examples, we continue to use findResults.txt.

## Grep -A n example 1

In this fist example, the first line is the command being used, followed by the output.

```
grep -A 3 "Bahamas" findResults.txt 
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Bali-History.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
--
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
--
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
```

As we can see, the command first gives us the path to the .txt files that contain the string "bahamas", however this time, it is proceeded by the three files
that come directly after it in the findResults.txt. We can see that after finding the first Bahamas file *WhereToGo.txt*, the files about Cancun, Bali, 
and Crete are next. Using this specific grep command, we can get a general sense of what information is proceeding our needed target file. 

## Grep -A n example 2

```
grep -A 4 "Barcelona" findResults.txt 
written_2/travel_guides/berlitz2/Barcelona-History.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
--
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt
--
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
```

In this second example, I am using grep -A to find the first 4 files that come after every file containing the word "Barcelona". As we can see from the
output, the grep command splits up every Barcelona file and its four proceeding files. In general, this command is not limited by only 3 or 4 lines, and can
be used to find multiple files in a directory that come exactly after the target file being searched for. This can be useful to see what information is
surrounding the desired files, which can help a user know if there is more information needed or if there are similar files from the one they are looking
for.

# Alternate command 3: grep - r

Normally when searching with grep, the command only checks to see if there is a matching pattern within file names or directories. While looking
for specific file names is useful, sometimes we would like to know more about the specific contents of the file. This is where grep -r comes into use.
Not only does it search directories and file names for a given pattern or phrase, it also looks deeper into subdirectories and into the actual
contents of the files that we wish to search. The functionality of the command can be given with the following examples.

## Grep -r example 1

```
grep -r -l "Cubans" written_2 
written_2/non-fiction/OUP/Castro/chR.txt
written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-History.txt

```

In this first example, we used the grep -r command to recursively search through all the files within the written_2 directory for the word "cubans".
While I used -r, its important to note that I also used -l, which is another command that simply lists file names. With this command, I was able
to find files whos contents included the word cubans. This is useful because instead of just looking within file names for a string pattern, we can actually
look inside the contents of files to find specific words or phrases. Another example of grep -r's functionality is shown below.

## Grep -r example 2

```
grep -r -l "Lucayans"
./written_2/travel_guides/berlitz2/Bahamas-History.txt
```

In this second example, I used the grep-r command to find the file containing the string "Lucayans". The command recursively searched through directories
and subdirectories to look through files and find the one who's contents included the word "Lucayans". In this particular instance, the grep -r command
was particularly useful because the resulting file *Bahamas-History.txt* was the only file that contained the wanted string. This comes to show that the
grep -r command is really useful if searching for extremely specific information, the kind which can't be reached with the regular grep command or other
related commands such as find.





