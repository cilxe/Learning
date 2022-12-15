# Windows Commands & Batch Scripts

### Commands

##### 1. **Apply to Current Commands Environment**
 <h1 id=1></h1>

   - [cd / chdir](#cd)
   - [chcp](#chcp)
   - [cmd](#cmd) [cmd.exe]
   - [echo](#echo)
   - [mode](#mode)
   - [set](#set)
   - [setx](#setx)
   - [if](#if)
   - [for](#for)
   - [goto](#goto)

##### 2. **Apply to System, Runing Programs**
<h1 id=2></h1>

   - [convert](#convert) [Disk Type]
   - [create](#create) [Partition | Volume]
   - [delete](#delete) [DIsk | Partition | Shadows | Volume]
   - [detail](#detail) [DIsk | Partition | Shadows | Volume]
   - [select](#select) [DIsk | Partition | Shadows | Volume]
   - [dism](#dism) [dism.exe]
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

##### 3. **Apply to Files**
   <h1 id=3></h1>

   - [attrib](#attrib)
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
| --- | ----------- |
| 437 | United States |
| 850 | Multilingual (Latin I) |
| 852 | Slavic (Latin II) |
| 855 | Cyrillic (Russian) |
| 857 | Turkish |
| 860 | Portuguese |
| 861 | Icelandic |
| 863 | Canadian-French |
| 865 | Nordic |
| 866 | Russian |
| 869 | Modern Greek |
| 936 | Chinese |


[<h3 id=cmd>CMD (cmd.exe)</h3>](#1)
Starts a new instance of the command interpreter, Cmd.exe.


[<h3 id=echo>ECHO</h3>](#1)
Displays messages or turns on or off the command echoing feature.
```
echo [on | off] 
:: Turns on or off the command showing features

echo <messages> 
:: Output the message text on the screen
```


[<h3 id=date-time>DATE & TIME</h3>](#2)
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