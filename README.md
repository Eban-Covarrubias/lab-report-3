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
Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
SERVICES OF SOUTHWEST VIRGINIA, INCORPORATED,
Plaintiffs-Appellants,
--
District of Virginia, at Big Stone Gap. James P. Jones, District
Judge. (CA-00-33-2)
Argued: February 28, 2001
--
Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
& BURLING, Washington, D.C., for Appellees. ON BRIEF: Andrew J.
Heimert, COVINGTON & BURLING, Washington, D.C.; Paul R.
--
Virginia, for Appellees.
Unpublished opinions are not binding precedent in this circuit.
See Local Rule 36(c).
--
Client Centered Legal Services of Southwest Virginia,
Incorporated and Hugh F. O'Donnell, its executive director
(collectively, "CCLS"), appeal an order of the district court
--
in the coalfields region of southwestern Virginia, has been an LSC
grantee since 1980.
O'DONNELL v. EIDLEMAN
```

Whenever a line with the word "Virginia" in it is found it is displayed, and the next 2 lines after it are also displayed. The number of
lines being displayed after are determined by the value of NUM. THis can be useful to find some more information about a certain topic that
is mentioned in a lengthier txt file.

Example b)

Input:
```
grep -A 8 "Virginia" ODonnell_et_al_v_LSCdecision.txt
```

Output:
```
Services of Southwest Virginia, Incorporated; CLIENT CENTERED LEGAL
SERVICES OF SOUTHWEST VIRGINIA, INCORPORATED,
Plaintiffs-Appellants,
� No. 00-1901
v.
JOHN EIDLEMAN, Program Specialist for the Legal Services
Corporation; LEGAL SERVICES CORPORATION; JOHN MCKAY, President of
the Legal Services Corporation,
Defendants-Appellees. �
--
District of Virginia, at Big Stone Gap. James P. Jones, District
Judge. (CA-00-33-2)
Argued: February 28, 2001
Decided: June 25, 2001
Before WILKINS and WILLIAMS, Circuit Judges, and HAMILTON,
Senior Circuit Judge.
Vacated and remanded with instructions by unpublished per curiam
opinion.
O'DONNELL v. EIDLEMAN
--
Virginia, for Appellants. Thomas Samuel Williamson, Jr., COVINGTON
& BURLING, Washington, D.C., for Appellees. ON BRIEF: Andrew J.
Heimert, COVINGTON & BURLING, Washington, D.C.; Paul R.
Thomson, Jr., WOODS, ROGERS & HAZLE-GROVE, P.L.C., Roanoke,
Virginia, for Appellees.
Unpublished opinions are not binding precedent in this circuit.
See Local Rule 36(c).


OPINION
PER CURIAM:
Client Centered Legal Services of Southwest Virginia,
Incorporated and Hugh F. O'Donnell, its executive director
(collectively, "CCLS"), appeal an order of the district court
granting judgment in favor of the Legal Services Corporation and
two of its officers (collectively, "the LSC") on CCLS's claims that
various actions by the LSC exceeded its statutory and regulatory
authority. For the reasons set forth below, we conclude that
Congress has not authorized judicial review of these claims. We
therefore vacate and remand with instructions to dismiss.
--
in the coalfields region of southwestern Virginia, has been an LSC
grantee since 1980.
O'DONNELL v. EIDLEMAN
This litigation involves CCLS's challenge to certain actions
taken by the LSC in connection with the LSC's consolidation of
services areas (undertaken as a cost-cutting measure) and
implementation of a competitive bidding program for grant money.
Following a bench trial, the district court rejected CCLS's claims
on the merits.
```

Here is another example with a large value of NUM, in this case the next 8 lines are printed out after finding a line with the
word "Virginia" in it. 


Citations:
https://chat.openai.com/
All of the information that I got about these options was purely from communication with chatGPT

# Here are the prompts I used and the outputs I got:
prompt:
teach me how to use grep linux command and all of its options
output:
![image](https://github.com/Eban-Covarrubias/lab-report-3/assets/130101682/0e6ae0a4-7c4d-44e8-b4d0-0cc4b9dda77c)

Using this output I decided which options were the most interesting and would be included on the report. I was also able to view additional 
options by following the advice at the bottom of the output recommending me to run the command grep --help. Once I picked several of the
options I sent in prompts to chatGPT asking it to give me a discription of what the command does with the specific option and to give an example of 
using it.

prompt:
show me an example of using grep with the -i option
output:
![image](https://github.com/Eban-Covarrubias/lab-report-3/assets/130101682/e700a4b2-2ec3-4300-a11a-a0c064965881)

Using this output I gave paraphrased brief description of the functionality of the command with the specified option and ran tests inspired by some of the tests 
that chatGPT showed me.

prompt:
show me an example of using the grep command with the -n option
output:
![image](https://github.com/Eban-Covarrubias/lab-report-3/assets/130101682/5b2087a2-44aa-42ff-870c-0faddb837ace)

Using this output I gave paraphrased brief description of the functionality of the command with the specified option and ran tests inspired by some of the tests 
that chatGPT showed me.

prompt:
show me an example of using grep command with the -m NUM option
output:
![image](https://github.com/Eban-Covarrubias/lab-report-3/assets/130101682/db171b25-6d7a-4345-ade7-8c88de105571)

Using this output I gave paraphrased brief description of the functionality of the command with the specified option and ran tests inspired by some of the tests 
that chatGPT showed me.

prompt:
show me an example of using grep with -A num option
output:
![image](https://github.com/Eban-Covarrubias/lab-report-3/assets/130101682/f54b6c53-6bfe-4066-8a9d-70056f141ebf)

Using this output I gave paraphrased brief description of the functionality of the command with the specified option and ran tests inspired by some of the tests 
that chatGPT showed me.







