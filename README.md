# Setup

Change into desired directory, clone the project and decompress passwords-hailmary.txt.zip.

**Example:**

`git clone https://github.com/webpwnized/byepass.git`

`cd bypass/passwords`

`unzip passwords-hailmary.txt.zip`

Verify config.py is properly configured. 

**JTR_FILE_PATH**: Install path for John the Ripper. This is
 system and situation dependent. On Kali Linux, the default 
 path is "/usr/share/john". When john is compiled natively,
 the path may be "/opt/john/run/" but the user who installed
 JTR could put it in others directories.

**JTR_EXECUTABLE_FILENAME**: Filename of the john executable. By default, this is 
"john" and should not need to be changed. On Windows it is john.exe by default.

**JTR_POT_FILENAME**: Filename of the john.pot file. By default, this is 
"john.pot" and should not need to be changed

If unsure of location of John the Ripper, try 

`locate john`

**Example:**

if locate finds john installed in /opt/john/run/

`locate john`

`/opt/john/run/`

Then the config.py should contain the following

`JTR_FILE_PATH = "/opt/john/run/"`

`JTR_EXECUTABLE_FILENAME = "john"`

`JTR_POT_FILENAME = "john.pot"`

# Usage

**PassTime: Automate statistical analysis of passwords in support of password cracking tasks**

**Usage**: passtime.py [-h] [-v] [-l] [-p PERCENTILE] [-a] -i INPUT_FILE

**Optional arguments:**

      -h, --help            show this help message and exit
      -v, --verbose         Enable verbose output
      -l, --list-masks      List password masks for the passwords provided in the INPUT FILE
      -p PERCENTILE, --percentile PERCENTILE
                            Based on statistical analysis of the passwords provided, only list masks matching the given PERCENTILE percent of passwords. For example, if a value of 0.25 provided, only lists the relatively few masks needed to crack 25 percent of the passwords. Ideally, these would be the only masks needed to crack the same percentage of the remaining, uncracked passwords. However, the prediction is only as good as the sample passwords provided in the INPUT FILE. The more closely the provided passwords match the target passwords, the better the prediction.
      -a, --analyze-passwords
                            Perform analysis on the password provided in the INPUT FILE. A probability density function (PDF) will be displayed with the masks matching PERCENTILE percent of passwords. The marginal and cummulative percentages represented by each mask are provided with the number of passwords matched by the mask.
      -i INPUT_FILE, --input-file INPUT_FILE
                            Path to file containing passwords to analyze

**Examples**:

List masks representing 75 percent of the passwords in input file worst-10000-passwords.txt

`python3 passtime.py -l -p 0.75 -i worst-10000-passwords.txt
`

Generate probability density function (PDF), masks, marginal percentile (MP), cummulative percentile (CP) and count of passwords representing 75 percent of the passwords in input file worst-10000-passwords.txt

`python3 passtime.py -a -p 0.75 -i worst-10000-passwords.txt
`
# Hashes and Cracked Hashes for Practice

These resources host hashes and the resulting passwords. These can be helpful for practice.

**Adeptus Mechanicus**: http://www.adeptus-mechanicus.com/codex/hashpass/hashpass.php

**Hashes.org**: https://hashes.org/leaks.php

# Educational Resources

**John the Ripper's cracking modes**: http://www.openwall.com/john/doc/MODES.shtml

**John the Ripper usage examples**: http://www.openwall.com/john/doc/EXAMPLES.shtml

**Luis Rocha's John the Ripper Cheat Sheet**: https://countuponsecurity.files.wordpress.com/2016/09/jtr-cheat-sheet.pdf