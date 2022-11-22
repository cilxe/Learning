# Windows Commands & Batch Scripts

#### Commands

1. **Apply to Current Commands Environment**
   
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

2. **Apply to System, Runing Programs**
   
   - convert [Disk Type]
   
   - create [Partition | Volume]
   
   - delete [DIsk | Partition | Shadows | Volume]
   
   - detail [DIsk | Partition | Shadows | Volume]
   
   - selete [DIsk | Partition | Shadows | Volume]
   
   - dism [dism.exe]
   
   - date
   
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

3. **Apply to Files**
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
# to a specified folder
cd [/d] <drive>:<path>  
chdir [/d] <drive>:<path>

# to parent folder
cd [..]  
chdir [..]
```

<h3 id=chcp>CHCP</h3>