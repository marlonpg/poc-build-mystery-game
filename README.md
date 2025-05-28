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

INTERVIEW
699607
Annabel Church  F       38      Buckingham Place, line 179
Interviewed Ms. Church at 2:04 pm.  Witness stated that she did not see anyone she could identify as the shooter, that she ran away as soon as the shots were fired.

However, she reports seeing the car that fled the scene.  Describes it as a blue Honda, with a license plate that starts with "L337" and ends with "9"

head -n 173 streets/Mattapan_Street | tail -n 1


# awk -v RS= '/Honda/ && /Blue/ && /L337.*9/' vehicles
## -v RS= sets the record separator to empty, making awk treat paragraphs (blocks separated by blank lines) as single records.
## pattern '/Honda/ && /Blue/ && /L337.*9/'

License Plate L337DV9
Make: Honda
Color: Blue
Owner: Joe Germuska
Height: 6'2"
Weight: 164 lbs

$ grep -i 'Joe Germuska' people
Joe Germuska    M       65      Plainfield Street, line 275


License Plate L3375A9
Make: Honda
Color: Blue
Owner: Jeremy Bowers
Height: 6'1"
Weight: 204 lbs

$ grep -i 'Jeremy Bowers' people
Jeremy Bowers   M       34      Dunstable Road, line 284


## Looking into memberships
- AAA Delta_SkyMiles Museum_of_Bash_History

$ cat AAA Delta_SkyMiles Museum_of_Bash_History | grep  "Jeremy Bowers"
Jeremy Bowers
Jeremy Bowers
Jeremy Bowers

$ echo "Jeremy Bowers" | $(command -v md5 || command -v md5sum) | grep -qif /dev/stdin encoded && echo CORRECT\! GREAT WORK, GUMSHOE. || echo SORRY, TRY AGAIN.    
CORRECT! GREAT WORK, GUMSHOE.