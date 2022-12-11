# Python-Notes

## Basic commands

### Install & uninstall package
```
  py -m pip install PACKAGE_NAME  
  py -m pip uninstall PACKAGE_NAME  
```
#### Install specific version packages
```
  py -m pip install PACKAGE_NAME=VERSION
```
#### Install packages from requirements files
```
  py -m pip install -r requirements.txt
```

### Python to Executable file [Pyinstaller](https://pyinstaller.org/en/stable/usage.html#using-pyinstaller)

#### [Start Generat](https://pyinstaller.org/en/stable/usage.html#what-to-generate)  

```
pyinstaller -D -F --specpath DIR -n exe_name myscript.py
```
or
```
pyinstaller --onedir --onefile --specpath DIR --name exe_name myscript.py
```
##### Windows Specified options
Build without console window
**-w, --windowed, --noconsole**
```
pyinstaller --onedir --onefile --specpath DIR --name exe_name --noconsole myscript.py
```
or [In Windows]
```
pyinstaller --onedir --onefile ^
      --specpath DIR ^
      --name exe_name ^
      --noconsole ^
      myscript.py
```

### [SubProcess](https://docs.python.org/3/library/subprocess.html)
 - run() 
 - Popen()
 - call()
 - check_call()
 - check_output()
 - communicate()

### [Used Python packages](https://pypi.org/)
 - 
 - [auto-py-to-exe](https://pypi.org/project/auto-py-to-exe/)
 - [pyinstaller](https://pypi.org/project/pyinstaller/)
 - [PyQt5](https://pypi.org/project/PyQt5/): &ensp;last support version for Windows 7/8
 - [PyQt6](https://pypi.org/project/PyQt5/)
 - [you-get](https://pypi.org/project/you-get/)
 - [yt-dlp](https://pypi.org/project/yt-dlp/)
 - 
