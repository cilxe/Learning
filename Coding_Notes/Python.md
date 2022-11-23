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

