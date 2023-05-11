# lab-report-3
### researching grep command:

# 1. Using the grep command with -i option.

Using the -i command makes the grep command ignore case sensitivity when matching patterns

Example a)

Command:
```
grep -i "virginia" ODonnell_et_al_v_LSCdecision.txt
```

Output:
```
Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
SERVICES OF SOUTHWEST VIRGINIA, INCORPORATED,
District of Virginia, at Big Stone Gap. James P. Jones, District
Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
Virginia, for Appellees.
Client Centered Legal Services of Southwest Virginia,
in the coalfields region of southwestern Virginia, has been an LSC
```

The reason that this command worked the way it did was because it searched through the txt file ODonnell_et_al_v_LSCdecision.txt and 
only displayed the lines that included the word virginia with no case sensitivity. This is why you can see that there are instances of 
the word virginia in the lines where there may be capital letters.

Example b)

Input:
```
grep -i "VIRGINIA" ODonnell_et_al_v_LSCdecision.txt

```

Output:
```
Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
SERVICES OF SOUTHWEST VIRGINIA, INCORPORATED,
District of Virginia, at Big Stone Gap. James P. Jones, District
Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
Virginia, for Appellees.
Client Centered Legal Services of Southwest Virginia,
in the coalfields region of southwestern Virginia, has been an LSC
```

This has the same exact output of before and does a great job of demonstrating the lack of case sensitivity that the -i option enforces.
The lines that include the word VIRGINIA with any modification to its captial letters or not are displayed as ouput.


# 2. Using the grep command with -n option.

The -n option with the grep command causes each matching line to start with its line number.

Example a)

Input:
```
grep -n "Virginia" ODonnell_et_al_v_LSCdecision.txt
```

Output:
```
9:Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
19:District of Virginia, at Big Stone Gap. James P. Jones, District
31:Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
35:Virginia, for Appellees.
42:Client Centered Legal Services of Southwest Virginia,
58:in the coalfields region of southwestern Virginia, has been an LSC
```

The way that this works is by selecting each line if it contains the word "Virginia" and then displaying the line that it appears in the 
ODonnell_et_al_v_LSCdecision.txt file. This makes it incredibly easy to find exacly which line contains which specific words without needing
to read through the file.

Example b)

Input:
```
grep -n "Regional Management" ODonnell_et_al_v_LSCdecision.txt
```

Output:
```
68:In our recent decision in Regional Management Corp. v. Legal
101:The reasoning of Regional Management is controlling here. As we
102:held in Regional Management, the LSCA was intended by Congress for
125:in Regional Management. See Reg'l Mgmt., 186 F.3d at 464.
```

This has very similar behavior, and is another example with a slightly more complex text to match.
Again you can see exacly which lines include the specified text.

# 3. Using the grep command with the -m NUM option

The -m NUM option allows you to limit the amount of displayed lines allowed to a value specified by NUM
This can be useful to get a quick preview or glace into how certain lines are used in a txt file.

Example a)

Input:
```
grep -m 3 "Virginia" ODonnell_et_al_v_LSCdecision.txt
```

Output:
```
Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
District of Virginia, at Big Stone Gap. James P. Jones, District
Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
```

The output has only 3 lines, this is expected because the value of NUM with the -m option is set to 3 meaning that
no more than three lines will be displayed. We know that there are more than 3 lines in the file that include the
word Virginia from previous examples, yet because of this option only the first 3 are displayed.

Example b)

Input:
```
grep -m 90 "Virginia" ODonnell_et_al_v_LSCdecision.txt
```

Output:
```
Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
District of Virginia, at Big Stone Gap. James P. Jones, District
Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
Virginia, for Appellees.
Client Centered Legal Services of Southwest Virginia,
in the coalfields region of southwestern Virginia, has been an LSC
```

This is an example showing how the number of lines is simply limited to the value of NUM not necessarily equal, therefore if there 
isn't enough lines the total number of lines could very easily be less than the value of NUM. This case displays that perfectly as
NUM is 90 yet there are 6 lines.

# 4 Using grep with -A NUM option

the -A NUM option allows lines to be selected and displayed by the grep function and then will also display the next NUM amount of lines.

Example a)

Input:
```
grep -A 2 "Virginia" ODonnell_et_al_v_LSCdecision.txt 
```

Output:
```
```
