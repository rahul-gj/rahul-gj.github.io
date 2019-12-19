# Very Basic Python Learning Guide.
Disclaimer: This article is based on author's point of view and doesn't reflect best practice.

## Setting up Python Environment on Windows 7/10

### Download python

[64bit](https://www.python.org/ftp/python/3.7.5/python-3.7.5-amd64.exe)

[32bit](https://www.python.org/ftp/python/3.7.5/python-3.7.5.exe)

for more information visit [official site](www.python.org/downloads)

### Install python
Install with default settings.

### create virtual environment and install development libraries
python installed system vide sould not be used for development and testing. you should always use python virtual environments so that if anything goes wrong, your system installation is not affected.

If python is installed with default settings it will be installed in `%LOCALAPPDATA%\Programs\Python\Python37`

Open windows command prompt (press win key and type cmd then enter).
By default it will be opened in home directory (Type `cd %userprofile%` if you want to make sure). Type following commands after that. Please note that every line is prefixed with `C:\Users\user.name> ` just for explanation. you only need to type (or copy/paste) text after that. for example in last line only `python` is need to typed not `(dev) C:\Users\user.name> python`.

Last line is optional. It will start pyton interpreter. to exit the interpreter type `exit()` and hit enter.


```cmd
C:\Users\user.name> %LOCALAPPDATA%\Programs\Python\Python37\python.exe -venv dev
C:\Users\user.name> dev\scripts\activate
(dev) C:\Users\user.name>
```

on successful virtual envirnment creation and activation your virtual name  (in our case `dev`) with parenthesis will appear before path in your command window. you can close the cmd after that. continue typing following command to install two module useful for development.

```cmd
(dev) C:\Users\user.name> pip install pylint yapf
```

It will take some time depending on your internet and computer speed. please do not close command prompt while installation is pending. you will be acknowledged after successful installation. You can read about [pylint](https://github.com/PyCQA/pylint) and [yapf](https://github.com/google/yapf)


### Download IDE (Integrated development environment)
[64bit](https://github.com/VSCodium/vscodium/releases/download/1.41.0/VSCodium-win32-x64-1.41.0.zip)

[32bit](https://github.com/VSCodium/vscodium/releases/download/1.41.0/VSCodium-win32-ia32-1.41.0.zip)

for more information visit [official site](https://vscodium.com/)


### Prepare IDE
- unzip `VSCodium-win32-x64-1.41.0.zip` to desired location. if possible unzip in `%LOCALAPPDATA%\Programs\vscodium`.

- install python extension for IDE
double click `VSCodium` executable. in customize section click python install python extension. (see image for more info)
<img src="/src/img/vscodium_python.png">

    Press ok in right hand down corner. it will take some time to install. Please do not click any more buttons if prompted.

- Select python environment
    got to File > Preferences > Settings and type python.pythonpath

    in the input field (where python is written) replace python with your virtual environment python path. it will be `C:\Users\user.name\dev\scripts\python`. You need to change user.name with your username. If you are lazy enought type `echo %userprofile%\dev\scripts\python` in cmd and python path will be printed. just copy that and paste it in above field. it hould look like this.
    <img src="/src/img/vscodium_settings_pythonpath.png">

