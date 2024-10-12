# Windows Console Commands
- ## [Command-line shells (Batch Script)](#1)
- ## [PowerShell](#ps)
- Miscrosoft Online Documentation
  - [Windows Commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
  - [PowerShell 5.1](https://learn.microsoft.com/en-us/powershell/scripting/overview?view=powershell-5.1)
  - [PowerShell 7.3](https://learn.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.3)
  
---
 <h2 id=1>1. Apply to Commands/System Environment</h2>
 
   - [cd / chdir](#cd)
   - [chcp](#chcp)
   - [cmd](#cmd) (cmd.exe)
   - [echo](#echo)
   - [mode](#mode)
   - [set](#set)
   - [setx](#setx)
   - [if](#if)
   - [for](#for)
   - [goto](#goto)


 <h2 id=2>2. Apply to System, Programs</h2>

   - [convert](#convert) [Disk Type]
   - [create](#create) [Partition | Volume]
   - [delete](#delete) [DIsk | Partition | Shadows | Volume]
   - [detail](#detail) [DIsk | Partition | Shadows | Volume]
   - [select](#select) [DIsk | Partition | Shadows | Volume]
   - [dism](#dism) (dism.exe)
   - [date & time](#date-time)
   - [ftp](#ftp)
   - [netsh](#netsh)
   - [ipconfig](#ipconfig)
   - [reg](#reg)
   - [sc](#sc)
   - [schtasks](#schtasks)
   - [shutdown](#shutdown)
   - [taskkill](#taskkill)
   - [wmic](#wmic)
   - [CheckNetIsolation: UWP App Network Manageent](#checkNetIsolation) [CheckNetIsolation.exe]

 <h2 id=3>3. Apply to Files</h2>

   - [attrib](#attrib)
   - [call](#call)
   - [certUtil](#certUtil)
   - [copy](#copy)
   - [del](#del)
   - [erase](#erase)
   - [dir](#dir)
   - [fc](#fc)  [fc.exe]
   - [find](#find) [String in file]
   - [findstr](#findstr)
   - [md](#md)
   - [mkdir](#mkdir)
   - [rd](#rd)
   - [rmdir](#rmdir)
   - [move](#move)
   - [rename](#rename)
   - [replace](#replace)


[<h3 id=cd>CD / CHDIR</h3>](#1)
Displays the name of the current directory or changes the current directory.
```
@REM locate to a specified folder
cd [/d] <drive>:<path>  
chdir [/d] <drive>:<path>

@REM locate to parent folder.

cd [..]  
chdir [..]
```
[<h3 id=chcp>CHCP</h3>](#1)
Changes the active console code page.
```
CHCP [nnn]

nnn: Specifies a code page number.
```
| Code page | Country/region or language |
| --------- | -------------------------- |
| 437       | United States              |
| 850       | Multilingual (Latin I)     |
| 852       | Slavic (Latin II)          |
| 855       | Cyrillic (Russian)         |
| 857       | Turkish                    |
| 860       | Portuguese                 |
| 861       | Icelandic                  |
| 863       | Canadian-French            |
| 865       | Nordic                     |
| 866       | Russian                    |
| 869       | Modern Greek               |
| 936       | Chinese                    |


[<h3 id=cmd>CMD (cmd.exe)</h3>](#1)
Starts a new instance of the command interpreter, CMD.exe.


[<h3 id=echo>ECHO</h3>](#1)
Displays messages or turns on or off the command echoing feature.
```
echo [on | off] 
:: Turns on or off the command showing features

echo <messages> 
:: Output the message text on the screen
```

[<h3 id=set>SET</h3>](#1)
Displays, sets, or removes cmd.exe environment variables. If used without parameters, set displays the current environment variable settings.  
```
set [<variable>=[<string>]]
set [/p] <variable>=[<promptString>]
set /a <variable>=<expression>

```




[<h3 id=for>FOR</h3>](#1)
**Syntax**
```
for {%% | %}<variable> in (<set>) do <command> [<commandlineoptions>]
```
**Parameters**
```
| Parameter            | Description                                                    |
| -------------------- | -------------------------------------------------------------- |
| {%% \| %}<variable>  | Create and call a variable by using % (%% within a batch file) |
| (<set>)              | One or more files/directories/text strings/a range of values   |
| <command>            | Do something to each file                                      |
| <commandlineoptions> | Specifies any command-line options                             |
| /?                   | Display help at the command-prompt                             |
```
**Remarks**
- Variable names are case sensitive, global, and no more than 52 at a time.
- %0~9 and %* target local files, to avoid thease parameters, using similar characters.
- Do commands to file with special characters ("$, (), "), make suer it parenthesised.
- FOR command extensions: 
  - /D : Directories only
   ```
   for /d {%%|%}<Variable> in (<Set>) do <Command> [<CommandLineOptions>]
   ```
 - /R : Recursive
   ```
   for /r [[<drive>:]<path>] {%%|%}<variable> in (<set>) do <command> [<commandlinepptions>]
   ``` 
 - /L : Iterating a range of values
   ```
   for /l {%%|%}<variable> in (<start#>,<step#>,<end#>) do <command> [<commandlinepptions>]
   ```
 - /F : Parsing consist reading the outpput, strings  or file content 
   ```
   for /f [<parsingkeywords>] {%%|%}<variable> in (<set>) do <command> [<commandlinepptions>]
   for /f [<parsingkeywords>] {%%|%}<variable> in (<literalstring>) do <command [<commandlinepptions>]
   for /f [<parsingkeywords>] {%%|%}<variable> in ('<command>') do <command> [<commandlinepptions>]
   ```
    

**Examples**
1. Any specified files (*.txt, *.docx, *.exe)
   ```
   FOR %i IN (*.txt *.exe *.dll *.log) DO ()

   FOR %i IN (a.txt b.doc c.md) DO ()

   FOR %i IN (a*.txt b*.doc) DO ()
   ```
2. Any files with drag & drop (%~1, %*)
   ```
   FOR %i IN (%~1) DO ()

   FOR %i IN (%*) DO ( <command> "%%~fi")
   ```
3. FOR /F with `USEBACKQ` Handle a range of strings
   ```
   FOR /F "tokens=* USEBACKQ" %%v IN (`commands`) DO (set "value=%%v")
   ```

#### [<h3 id=date-time>DATE & TIME</h3>](#2)
Displays or sets the system date & time.
```
@REM Get Current Date & Time
%date% %time%

@REM Get formatting date & time
%date:~x,y%  & %time:~x,y%  [x] start, [y] count

@REM Specify the Date & Time format
echo %date:~0,4%-%date:~5,2%-%date:~8,2%
2001-01-01

echo %time:~0,2%:%time:~3,2%:%time:~6,2%
10:00:00
```
#### [<h3 id=checkNetIsolation>CheckNetIsolation: UWP App Network Manageent</h3>](#2)

##### **Apply proxy exemption to UWP apps**
1. Method 1: apply a single app with its SID
```
# Find UWP App SID from Registry [Win + R > regedit]
HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppContainer\Mappings\

# Find UWP App package name in Powershell
powershell get-appxpackage *AppName

# Apply setting to app with SID or PackageName
# SID from above     # AppPackageName find with powershell
CheckNetIsolation loopbackexempt -a -p=SID
CheckNetIsolation loopbackexempt -a -n=AppPackageName
```
2. Method 2: Apply to all with for loop
```
FOR /F "tokens=11 delims=\" %s IN ('REG QUERY "HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppContainer\Mappings"') DO CheckNetIsolation LoopbackExempt -a -p=%s
```

[<h3 id=call>CALL</h3>](#3)
#### **Syntax**

```
call [drive:][path]<filename> [<batchparameters>]] 
call [:<label> [<arguments>]]
```
#### **Batch Parameters** [(Learn more)](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/call#batch-parameters)
| Batch Parameter | Description                                                          |
| --------------- | -------------------------------------------------------------------- |
| %~1             | Expands %1 and removes surrounding quotation marks.                  |
| %~f1            | Expands %1 to a fully qualified path.                                |
| %~d1            | Expands %1 to a drive letter only.                                   |
| %~p1            | Expands %1 to a path only.                                           |
| %~n1            | Expands %1 to a file name only.                                      |
| %~x1            | Expands %1 to a file name extension only.                            |
| %~s1            | Expands %1 to a fully qualified path that contains short names only. |
| %~a1            | Expands %1 to the file attributes.                                   |
| %~t1            | Expands %1 to the date and time of file.                             |
| %~z1            | Expands %1 to the size of the file.                                  |
| %~dp1           | Expands %1 to a drive letter and path only.                          |
| %~nx1           | Expands %1 to a file name and extension only.                        |
| %~ftza1         | Expands %1 to display output similar to the dir command.             |


#### Example
```
#Single file
SET file=%~1

#Multiple files
SET files=%*

# Read multiple files
FOR %%i IN (%*) do ()
```

[<h3 id=certUtil>CertUtil</h3>](#3)

[<h3 id=find>Find</h3>](#3)

[<h3 id=findstr>findstr</h3>](#3)

<h1 id=ps>PowerShell</h1>
