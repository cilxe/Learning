# Windows Commands & Batch Scripts

### Commands

##### 1. **Apply to Current Commands Environment**
   
   - [cd / chdir](#cd)
   - [chcp](#chcp)
   - cmd
   - echo
   - mode
   - set
   - setx
   - if
   - for
  
   - goto

##### 2. **Apply to System, Runing Programs**
   
   - convert [Disk Type]
   
   - create [Partition | Volume]
   
   - delete [DIsk | Partition | Shadows | Volume]
   
   - detail [DIsk | Partition | Shadows | Volume]
   
   - selete [DIsk | Partition | Shadows | Volume]
   
   - dism [dism.exe]
   
   - [date](#date)
   
   - time
   
   - ftp
   
   - netsh
   
   - ipconfig
   
   - reg
   
   - sc
   
   - schtasks
   
   - shutdown
   
   - taskkill
   
   - wmic

##### 3. **Apply to Files**
   - attrib

   - certUtil

   - copy

   - del

   - erase

   - dir

   - fc  [fc.exe]

   - find  [String in file]

   - findstr

   - md

   - mkdir

   - rd

   - rmdir

   - move

   - rename

   - replace


<h3 id=cd>CD / CHDIR</h3>

Default without parameter — Display the name of the current folder.
```
@REM locate to a specified folder
cd [/d] <drive>:<path>  
chdir [/d] <drive>:<path>

@REM locate to parent folder.

cd [..]  
chdir [..]
```

<h3 id=date>DATE</h3>

Get current system date & time
```
@REM Get Current Date & Time  
@REM %date% %time%
@REM Get formatting date & time
@REM %date:~x,y%  & %time:~x,y%  [x] start, [y] count

@REM echo %date:~0,4%-%date:~5,2%-%date:~8,2%
@REM 2001-01-01
@REM echo %time:~0,2%:%time:~3,2%:%time:~6,2%
@REM 10:00:00

```