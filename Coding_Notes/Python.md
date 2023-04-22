# Python-Notes

## Basic commands

**Install & uninstall package**
```
py -m pip install PACKAGE_NAME  
py -m pip uninstall PACKAGE_NAME  
```
**Install specific version packages**
```
py -m pip install PACKAGE_NAME=VERSION
```
**Install packages from requirements files**
```
py -m pip install -r requirements.txt
```

### [SubProcess](https://docs.python.org/3/library/subprocess.html)
- run() 
- Popen()
- call()
- check_call()
- check_output()
- communicate()

### Python Formatting

### [Python Package Index (PyPi)](https://pypi.org/)
- 
- [auto-py-to-exe](#autopytoexe)
 - [Pip package](https://pypi.org/project/auto-py-to-exe/)
- [pyinstaller](#pyinstaller)
 - [Pip package](https://pypi.org/project/pyinstaller/)
- [PyQt5]
 - [Homepage](https://pypi.org/project/PyQt5/)
 - Last version for support Windows 7/8
- [PyQt6]
 - [Homepage](https://pypi.org/project/PyQt6/)
- [you-get]
 - [Pip package](https://pypi.org/project/you-get/)
- [yt-dlp]
 - [Pip package](https://pypi.org/project/yt-dlp/)
- [VirtualEnv](#virtualenv)
 - [Pip package]()



<h3 id=autopytoexe>auto-py-to-exe</h3>

<h3 id=pyinstaller>Python to Executable file</h3>

- [Pyinstaller](https://pyinstaller.org/en/stable/usage.html#using-pyinstaller) 
    ```
    pyinstaller -D -F--specpath DIR -n exe_name myscript.py
    ```
    or
    ```
    pyinstaller --onedir --onefile --specpath DIR --name exe_name myscript.py
    ```
    **Windows Specified options**  
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

<h3 id=virtualenv>Python Virtual Environment - virtualenv</h3>

## General Guidance
1. Install **virtualenv** from Pip
```
python -m pip install --user virtualenv
```
2. Creating virtual environments from a local directory
```
python -m venv /path/to/new/virtualenvs
```
3. Ativate the virtual environment  
Run **activate.bat** under the "Scripts" directory  
Or just run the following commands in Command Prompt:
```
[Drive:]/path/to/new/virtualenvs/scripts/activate.bat

```

