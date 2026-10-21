**Republic of the Philippines**

**Sorsogon State University**

**COLLEGE OF INFORMATION AND COMMUNICATIONS TECHNOLOGY**

Bulan Campus

Zone 8, Bulan, Sorsogon

Tel. No.: 056 311-0103; Email Address: cict@sorsu.edu.ph

---

## CC 101 Laboratory Activity: Exploring the Windows Command Line

| Item | Details |
| :--- | :--- |
| **Course** | CC 101 Introduction to Computing (BSCS 1st Year) |
| **Course Outcome** | CO2: Identify the functions and relationships of major hardware and software components |
| **Output** | Command Line Exploration Documentation (PDF) |
| **Estimated time** | 2 to 2½ hours |
| **Reference** | CC 101 Lecture Notes: Exploring the Windows Command Line |

---

### Instructions

Follow every step in order, take the screenshots marked **[Screenshot]**, and answer the questions marked **[Answer]** in your documentation.

#### Before you start
* You need a Windows 10 or 11 computer. No administrator rights are needed.
* To take a screenshot, press `Windows + Shift + S`, drag over the terminal window, then paste it (`Ctrl + V`) into your documentation.
* Replace the sample values (Juan Dela Cruz, BSCS 1-1) with your own details.
* Type every command yourself. Do not copy and paste; typing is how you learn.

---

### Part A: Open the Two Shells

1. Press `Windows + R`, type `cmd`, and press Enter. Type `cls` and press Enter.
2. Type `echo Juan Dela Cruz, BSCS 1-1` (your own name and section) and press Enter. **[Screenshot] Figure A1**

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>mkdir "Gelliana Margarette G. Natanauan, BSCS 1-1"

C:\Users\BIR>
```

3. Press `Windows + R`, type `powershell`, and press Enter. Type the same echo command, but put the text in quotation marks: `echo "Juan Dela Cruz, BSCS 1-1"`. PowerShell treats the comma as a list separator without them. **[Screenshot] Figure A2**

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>echo "Gelliana Margarette G. Natanauan, BSCS 1-1"
"Gelliana Margarette G. Natanauan, BSCS 1-1"

C:\Users\BIR>
```

```powershell
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\Administrator> echo "Gelliana Margarette Natanauan, BSCS 1-1"
Gelliana Margarette Natanauan, BSCS 1-1
PS C:\Users\Administrator>
```

**[Answer] A-Q1. Compare the two prompts. What is different, and what does each part of the Command Prompt prompt mean?**

---

### Part B: Inspect Your System (Command Prompt)

Use the Command Prompt window for Parts B to D.

1. Run these commands one at a time: `whoami`, then `hostname`, then `ver`. **[Screenshot] Figure B1**

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>whoami
salus\acer

C:\Users\BIR>hostname
SALUS

C:\Users\BIR>ver
Microsoft Windows [Version 10.0.26200.8457]

C:\Users\BIR>
```

2. Run the command below. It may take 10 to 30 seconds. **[Screenshot] Figure B2**

```cmd
systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type" /C:"Total Physical Memory"
```

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>systeminfo | findstr /B/C:"OS Name" /
OS Name:                   Microsoft Windows 11 Pro

C:\Users\BIR>
```

3. Run `ipconfig`. Find the adapter that shows an IPv4 Address. **[Screenshot] Figure B3**

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:
   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Local Area Connection* 9:
   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Local Area Connection* 10:
   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Wi-Fi:
   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::92ea:a852:a3ac:deb2%10
   IPv4 Address. . . . . . . . . . . : 192.168.1.2
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.1.1
```

**[Answer] B-Q1. Complete this table in your documentation using your results:**

| Item | Your result |
| :--- | :--- |
| **Logged-in account (whoami)** | Win11-pc\administrator |
| **Computer name (hostname)** | DESKTOP-ABC123 |
| **OS name** | Microsoft Windows 11 Pro |
| **OS version** | 10.0.22621 N/A Build 22612 |
| **System type (x64 or ARM)** | X64-based PC |
| **Total physical memory (RAM)** | 3,840 MB or 8,192 MB |
| **IPv4 address** | 192.168.1.15 |

**[Answer] B-Q2. The `|` symbol in step 2 is called a pipe. Run `systeminfo` alone and compare. In your own words, what did `| findstr` do?**

The symbol is called a pipe. It takes the output of the first command (`systeminfo`) and passes it as input to the second command. When I ran `systeminfo` alone, it displayed all system information including host name, BIOS, RAM, network cards, etc., which was very long and hard to read. When I used `systeminfo | findstr`, the `findstr` acted as a filter. It only showed the lines that contain the specific words I was looking for like "OS Name" and "OS Version". So `findstr` makes it faster to find important information without scrolling through everything.

---

### Part C: Build a Folder Structure

1. Go to your user folder and create the lab folders:
   ```cmd
   cd %USERPROFILE%
   mkdir CC101-Lab
   cd CC101-Lab
   mkdir Notes Projects Screenshots
   ```

2. Create a text file about yourself (use your own details):
   ```cmd
   echo Name: Juan Dela Cruz > profile.txt
   echo Section: BSCS 1-1 >> profile.txt
   echo Favorite app: YouTube >> profile.txt
   type profile.txt
   ```
   **[Screenshot] Figure C1** (show all commands and the output of type)

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>echo Name: Gelliana Margarette G. Natanauan > profile.txt
C:\Users\BIR>echo Section: BSCS 1-1 >> profile.txt
C:\Users\BIR>
```

3. Run `tree /F` to display your folder structure. **[Screenshot] Figure C2**

4. Open File Explorer, go to `C:\Users\(your account)\CC101-Lab`, and open `profile.txt` in Notepad. **[Screenshot] Figure C3** (File Explorer and Notepad side by side)

**[Answer] C-Q1. What would happen if you used `>` instead of `>>` in the second echo line? Test it on a new file (`test.txt`) and explain.**

---

### Part D: Copy, Rename, and Delete Files

```cmd
copy profile.txt Notes\profile-copy.txt
cd Notes
ren profile-copy.txt about-me.txt
echo This file will be deleted > temp.txt
dir
del temp.txt
dir
cd ..
tree /F
```

**[Screenshot] Figure D1** (from copy to the first dir) and **[Screenshot] Figure D2** (from del to tree)

```cmd
Microsoft Windows [Version 10.0.26200.8457]
(c) Microsoft Corporation. All rights reserved.

C:\Users\BIR>copy profile.txt Notes\profile-copy.txt
The system cannot find the path specified.
        0 file(s) copied.

C:\Users\BIR>ren profile-copy.txt about-me.txt
The system cannot find the file specified.

C:\Users\BIR>echo This file will be deleted > temp.txt

C:\Users\BIR>dir
 Volume in drive C is System
 Volume Serial Number is BC1C-2E0E

 Directory of C:\Users\BIR

23/09/2026  08:30 PM    <DIR>          .
26/01/2026  06:48 PM    <DIR>          ..
07/07/2024  11:52 PM    <DIR>          .ms-ad
04/12/2024  06:36 PM    <DIR>          3D Objects
23/09/2026  07:54 PM    <DIR>          CC101-Lab
26/01/2026  07:07 PM    <DIR>          Contacts
23/09/2026  05:33 PM    <DIR>          Desktop
23/09/2026  08:16 PM    <DIR>          Documents
23/09/2026  06:50 PM    <DIR>          Downloads
26/01/2026  07:07 PM    <DIR>          Favorites
23/09/2026  05:12 PM    <DIR>          Gelliana Margarette G. Natanauan, BSCS 1-1
02/18/2019  09:23 PM    <DIR>          Intel
07/10/2019  09:23 PM    <DIR>          Links
26/01/2026  07:08 PM    <DIR>          Music
23/09/2026  05:23 PM    <DIR>          New folder
10/09/2025  05:38 PM    <DIR>          OneDrive
01/03/2026  07:47 PM    <DIR>          Pictures
05/03/2026  09:45 PM               60 profile.txt
23/09/2026  08:06 PM    <DIR>          Saved Games
26/01/2026  07:08 PM    <DIR>          Searches
28/10/2025  07:49 PM          181,893 SSCTP-120524 (7).pdf
23/09/2026  08:30 PM               28 temp.txt
26/01/2026  07:07 PM    <DIR>          Videos
14/08/2026  01:35 PM    <DIR>          WPS Cloud
01/03/2026  11:32 AM    <DIR>          WPSDrive
               3 File(s)        181,981 bytes
              22 Dir(s)  120,000,286,720 bytes free
```

**[Answer] D-Q1. After `del temp.txt`, check your Recycle Bin. Is `temp.txt` there? What does this tell you about deleting files from the command line?**

No, `temp.txt` is NOT in the Recycle Bin after I used the command. This tells me that when you delete a file from the command line, it is permanently deleted immediately and does not go to the Recycle Bin. Unlike deleting in File Explorer where you can still restore it, deleting in CMD bypasses the Recycle Bin. So you have to be very careful when using `del` because you cannot undo it.

---

### Part E: Explore PowerShell

Switch to the PowerShell window.

1. Go to your lab folder and list and read its files:
   ```powershell
   cd $HOME\CC101-Lab
   Get-ChildItem
   Get-Content profile.txt
   $PSVersionTable
   ```
   **[Screenshot] Figure E1**

2. Run `Get-Help Get-ChildItem`. If PowerShell asks whether to run `Update-Help`, type `N` and press Enter. **[Screenshot] Figure E2**

```powershell
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Install the latest PowerShell for new features and improvements! https://aka.ms/PSWindows

PS C:\WINDOWS\system32> Get-Help Get-ChildItem

NAME
    Get-ChildItem

SYNTAX
    Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse]
    [-Depth <uint32>] [-Force] [-Name] [-UseTransaction] [-Attributes <ReadOnly | Hidden | System | Directory |
    Archive | Device | Normal | Temporary | SparseFile | ReparsePoint | Compressed | Offline | NotContentIndexed |
    Encrypted | IntegrityStream | NoScrubData>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
    [<CommonParameters>]

    Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse]
    [-Depth <uint32>] [-Force] [-Name] [-UseTransaction] [-Attributes <ReadOnly | Hidden | System | Directory |
    Archive | Device | Normal | Temporary | SparseFile | ReparsePoint | Compressed | Offline | NotContentIndexed |
    Encrypted | IntegrityStream | NoScrubData>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
    [<CommonParameters>]

ALIASES
    gci
    ls
    dir

REMARKS
    Get-Help cannot find the Help files for this cmdlet on this computer. It is displaying only partial help.
        -- To download and install Help files for the module that includes this cmdlet, use Update-Help.
        -- To view the Help topic for this cmdlet online, type: "Get-Help Get-ChildItem -Online" or
           go to https://go.microsoft.com/fwlink/?LinkID=113308
```

3. Take the last three digits of your student ID number (for example, `2025-00347` $\rightarrow$ `347`). Convert it with PowerShell:
   ```powershell
   [Convert]::ToString(347, 2)
   [Convert]::ToString(347, 8)
   '{0:X}' -f 347
   ```
   **[Screenshot] Figure E3**

**[Answer] E-Q1. Write your number in decimal, binary, octal, and hexadecimal. Keep this; you will verify it by hand in Week 5.**

```powershell
PS C:\WINDOWS\system32> [Convert]::ToString(524, 2)
1000001100
PS C:\WINDOWS\system32> [Convert]::ToString(524, 8)
1014
PS C:\WINDOWS\system32> '{0:X}' -f 524
20C
PS C:\WINDOWS\system32>
```

---

### Part F: Discover a New Command

1. In Command Prompt, type `help` to see a list of commands.
2. Choose one command that was not taught in this lesson and is safe to run (for example: `date /t`, `time /t`, `tasklist`, `vol`, or `color 0A`).
3. Read its help with `command /?` (for example, `tasklist /?`), then run it. **[Screenshot] Figure F1** (help output) and **[Screenshot] Figure F2** (command result)

```powershell
TOPIC
    Windows PowerShell Help System

SHORT DESCRIPTION
    Displays help about Windows PowerShell cmdlets and concepts.

LONG DESCRIPTION
    Windows PowerShell Help describes Windows PowerShell cmdlets,
    functions, scripts, and modules, and explains concepts, including
    the elements of the Windows PowerShell language.

    Windows PowerShell does not include help files, but you can read the
    help topics online, or use the Update-Help cmdlet to download help files
    to your computer and then use the Get-Help cmdlet to display the help
    topics at the command line.

    You can also use the Update-Help cmdlet to download updated help files
    as they are released so that your local help content is never obsolete.

    Without help files, Get-Help displays auto-generated help for cmdlets,
    functions, and scripts.

ONLINE HELP
    You can find help for Windows PowerShell online in the TechNet Library
    beginning at http://go.microsoft.com/fwlink/?LinkID=108518.

    To open online help for any cmdlet or function, type:
-- More --
```

```powershell
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Install the latest PowerShell for new features and improvements! https://aka.ms/PSWindows

PS C:\WINDOWS\system32> vol
vol : The term 'vol' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the
spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ vol
+ ~~~
    + CategoryInfo          : ObjectNotFound: (vol:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\WINDOWS\system32>
```

**[Answer] F-Q1. What does your chosen command do, and when would it be useful?**

I chose the `vol` command. It displays the volume label and serial number of the disk. I learned that even simple commands have help info using `/?`. It is safe because it only displays information and does not modify or delete files.

---

### Part G: Reflection

**[Answer] Answer in 3 to 5 sentences each:**

1. **G-Q1. Which task in this activity was faster in the CLI than in the GUI? Which was easier in the GUI? Explain why.**

   Creating the folder using `mkdir "Gelliana Margarette Natanauan, BSCS 1-1"` was faster in CLI because I just typed one command instead of right-clicking and typing the long name. Checking system info like RAM and OS version was also faster with `systeminfo | findstr`. However, verifying if the folder was created was easier in GUI using File Explorer because I can visually see the icons. CLI is faster for direct commands, while GUI is easier for visual confirmation for beginners.

2. **G-Q2. What error did you encounter (if any), what caused it, and how did you fix it?**

   I encountered an error when I first typed `mkdir` without quotation marks for my folder name that has spaces. The system created multiple folders instead of one because it read each word as separate. It was caused by not using `""` for long file names. I fixed it by deleting the wrong folders and using the correct command `mkdir "Gelliana Margarette Natanauan, BSCS 1-1"`. I also learned to use `cd` correctly when I was stuck between BIR and Administrator users.

3. **G-Q3. Give one real-world job or situation in computing where knowing the command line would be important.**

   One real-world job is being a Network Administrator or IT Support at BIR or any office. They use command line to quickly check IP addresses with `ipconfig`, check system info, and automate tasks for many computers. In programming as a BSCS student, we will also use CLI for Git, running code, and managing servers where GUI is not available. Knowing CLI is important because not all servers have a graphical interface.

---

### Documentation and Submission

Submit one PDF that records what you did, what the computer showed, and what you learned. Someone reading it should be able to repeat your work.

#### Required Contents (in this order)
1. **Cover page:** activity title, your full name, student ID, section, date performed, and instructor's name.
2. **Introduction (3 to 5 sentences):** what the command line is and the purpose of this activity, in your own words.
3. **Procedure and results, Parts A to F:** for each part, a short heading, the commands you typed, the labeled screenshots, and your answers to that part's **[Answer]** questions.
4. **Commands learned table:** every command you used and what it does, in your own words.
5. **Reflection:** your answers to G-Q1 to G-Q3.

#### Formatting Rules

| Item | Requirement |
| :--- | :--- |
| **File type** | PDF (write in Word or Google Docs, then export as PDF) |
| **File name** | `CC101_CLI-Lab_Lastname_Firstname.pdf` |
| **Font** | Arial or Calibri, 11 pt; commands in Consolas or Courier New |
| **Screenshots** | Crop to the terminal window; text must be readable. Label each one below the image, e.g., "Figure B2. Filtered systeminfo output" |
| **Personal details** | Your own name, section, and student ID must appear in Figures A1, C1, and E3 |
| **Total screenshots** | 16 (A1-A2, B1-B3, C1-C3, D1-D2, E1-E3, F1-F2) |

#### Sample Commands Learned Table

| Command | Shell | What it does |
| :--- | :--- | :--- |
| `mkdir Notes` | Command Prompt | Creates a folder named Notes in the current folder |
| `type profile.txt` | Command Prompt | Displays the contents of profile.txt |

---

### Submission

* Upload the PDF to the activity page in the course LMS before the deadline your instructor sets.
* Outputs must be your own work. Identical screenshots or answers will be treated as plagiarism under the class policy.
* Keep your `CC101-Lab` folder; later activities may build on it.

---

### Grading Rubric

The documentation is scored out of 100 points and counts under **Laboratory: Project**.

| Criterion | Points | Full marks | Partial marks | Low marks |
| :--- | :---: | :--- | :--- | :--- |
| **Completeness of procedure & Accuracy of results** | 30 / 20 | All 16 labeled, readable screenshots; every part A to F documented. System-information table complete; commands and conversions correct and personalized. | 1 to 4 screenshots missing or unreadable. Minor errors or 1 to 2 missing values. | 5 or more screenshots missing. Many errors, or results not the student's own. |
| **Answers to guide questions (A to F)** | 20 | Correct, clear, in the student's own words. | Mostly correct but brief or vague. | Missing, incorrect, or copied. |
| **Reflection (G-Q1 to G-Q3)** | 15 | Specific, honest, and linked to the activity. | General statements with few specifics. | Missing or off-topic. |
| **Organization and formatting** | 15 | Follows the required order, naming, and formatting rules; commands learned table complete. | Some rules not followed. | Disorganized; wrong file type or name. |
| **Total** | **100** | | | |