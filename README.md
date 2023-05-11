# lab-report-3
### researching grep command:

1. Using the grep command with -i option.



a) Using the -i command makes the grep command ignore case sensitivity when matching patterns

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


