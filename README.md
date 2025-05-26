# poc-build-mystery-game


There's been a murder in Terminal City, and TCPD needs your help.
To figure out whodunit, go to the 'mystery' subdirectory and start working from there.
You'll want to start by collecting all the clues at the crime scene (the 'crimescene' file).
The officers on the scene are pretty meticulous, so they've written down EVERYTHING in their officer reports.
Fortunately the sergeant went through and marked the real clues with the word "CLUE" in all caps.
If you get stuck, open one of the hint files (from the CL, type 'cat hint1', 'cat hint2', etc.).
To check your answer or find out the solution, open the file 'solution' (from the CL, type 'cat solution').
To get started on how to use the command line, open cheatsheet.md or cheatsheet.pdf (from the command line, you can type 'nano cheatsheet.md').
Don't use a text editor to view any files except these instructions, the cheatsheet, and hints.


CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for AAA, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.



sed -n '226p' mystery/streets/Glenwood_Avenue

grep -i Annabel mystery/people