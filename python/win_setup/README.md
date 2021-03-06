# Very Basic Python Setup and Learning Guide on Windows.
Disclaimer: This article is based on my personal opinion and does not reflect best practice.

Python is very easy to learn programming language. As per [StackOverflow developer suvey 2019](https://insights.stackoverflow.com/survey/2019), Python is the fastest-growing major programming language today. [Python outranked Java as the second most popular language on GitHub by repository contributors](https://octoverse.github.com/) in late 2019.

But when it comes to setting up pyton on windows for begginers, it is little difficult. Lets make it easy.

## Setting up Python Environment on Windows 7/10

### Download python
The Pyton 3.8.1 is latest but we should use python 3.7 series now for stability and compatibility and switch to python 3.8 later. Python 3.7.6 is latest stable version. Download it from below links. 64 bit version is reccomended. If you are confused use universal 32 bit version.

[64bit](https://www.python.org/ftp/python/3.7.6/python-3.7.6-amd64.exe)

[32bit](https://www.python.org/ftp/python/3.7.6/python-3.7.6.exe)

For more information visit [official site](https://www.python.org/downloads)

### Install python
Note: The images are for python 3.7.5, but it aplies to python 3.7.6.

If you have admin rights (your personal PC), install with default settings.

<img src="src/img/py_default-min.png" width="400">

If you do not have admin rights (work pc), uncheck `Install launcher for all users (recommended)`

<img src="src/img/py_noadmin-min.png" width="400">

<img src="src/img/py_installing-min.png" width="400">
<img src="src/img/py_installed-min.png" width="400">


### Create virtual environment and install development libraries
Python installed system vide should not be used for development and testing. You should always use python virtual environments so that if anything goes wrong, your system installation is not affected.

If python is installed with default settings it will be installed in `C:\Users\{user.name}>appdata\local\programs\python\python37`

Open windows command prompt (Go to `All Programs>Accesories>Command Prompt` or press <kbd>⊞ Win</kbd> and type cmd then hit <kbd>Enter</kbd> or press <kbd>⊞ Win</kbd>+<kbd>R</kbd>, type cmd and hit <kbd>Enter</kbd>).
By default, it will be opened in home directory. Type following commands after that. Please note that every line is prefixed with `C:\Users\{user.name}> ` just for explanation. You only need to type (or copy/paste) text after that. For example in last line, only `dev\scripts\activate` is need to be typed not `C:\Users\{user.name}> dev\scripts\activate`. `{user.name}` placeholder is for your understanding and it means your username jayvir or ashish or whatever your user name is. You can guess the username when you start cmd by above methods as it will be prefixed on every command you type. The prefix in your command prompt denotes in which directory you are in.

```cmd
C:\Users\{user.name}> %LOCALAPPDATA%\Programs\Python\Python37\python -m venv dev
C:\Users\{user.name}> dev\scripts\activate
```

**Explanation**:

- First line `%LOCALAPPDATA%\Programs\Python\Python37\python -m venv dev` is for creating python virtual environment by calling `python -m venv dev`. As our python executable is in `C:\Users\{user.name}>appdata\local\programs\python\python37` we need to include full path. `%LOCALAPPDATA%` is one of the [windows environment variables](https://ss64.com/nt/syntax-variables.html) which is expanded to `C:\Users\{user.name}>appdata\loca`.
    
- On second line we activate the created virtual environment bu typing `dev\scripts\activate`. As we have ran `python -m venv dev` in home directory, new python virtual environment named `dev` will be created in `C:\Users\{user.name}>dev`. As we are already on home path when we start `cmd`, we can use relative paths. The full path for above command will be `C:\Users\{user.name}\dev\scripts\activate` (which is also valid).

On successful virtual environment creation and activation your virtual name (in our case `dev`) with parenthesis will appear before path in your command window.

<img src="src/img/venv_active-min.png" width="400">

Continue typing following command to install two module useful for development (IDE integration).

```cmd
(dev) C:\Users\{user.name}> pip install pylint yapf
```

It will take some time depending on your internet speed. Please do not close command prompt during installation. You will be acknowledged after successful installation. You can read about [pip](https://docs.python.org/3.7/installing/index.html), [pylint](https://github.com/PyCQA/pylint) and [yapf](https://github.com/google/yapf)


### Download IDE (Integrated development environment)
As per [StackOverflow developer suvey 2019](https://insights.stackoverflow.com/survey/2019#technology-_-most-popular-development-environments), Visual Studio Code (VSCode) is most popular development environment. VSCodium is free binary distribution of VSCode with clean licence. Download it from below links.

[64bit](https://github.com/VSCodium/vscodium/releases/download/1.41.0/VSCodium-win32-x64-1.41.0.zip)

[32bit](https://github.com/VSCodium/vscodium/releases/download/1.41.0/VSCodium-win32-ia32-1.41.0.zip)

For more information visit [official site](https://vscodium.com/)


### Prepare IDE
- unzip zip file (`VSCodium-win32-x64-1.41.0.zip`) to desired location. if possible unzip in `%LOCALAPPDATA%\Programs\vscodium`.

- install python extension for IDE

    Double click `VSCodium` executable. In customize section click python install python extension. (See image for more info)
<img src="src/img/vscodium_python-min.png">

Press ok in right hand down corner. It will take some time to install. Please do not click any more buttons if prompted.

- Select python environment

    Go to File > Preferences > Settings and type python.pythonpath

    In the input field (where python is written), replace python with your virtual environment python path. it will be `C:\Users\{user.name}\dev\scripts\python`. You need to change {user.name} with your username. If you are lazy, enough type `echo %userprofile%\dev\scripts\python` in cmd and python path will be printed. Just copy that and paste it in above field. It should look like this.
    <img src="src/img/vscodium_settings_pythonpath-min.png">

close settings. Press `ctrl+N` for new file. Type `print('Hello world')`, press `ctrl+S`, save as hello.py to anywhere you want.

To run python program, open cmd and type following.

```cmd
C:\Users\{user.name} > dev\Scripts\activate
(dev) C:\Users\rahulkumar.patel > python path\to\your\hello.py
```

You need to change `path\to\your\hello.py` to real path of your above saved file. To copy file path of any file in windows, highlight file single click, press and hold `shift` key and right click on file then select `copy as path` option.

It will be handy if you have enabled file extensions for known files in windows. Please click [here](How to Make Windows Show File Extensions) if you don't know how?

Thats it. Happy coding.

### Learning python

Python is very easy to learn.

[Introduction to Python on UDACITY](https://www.udacity.com/course/introduction-to-python--ud1110) is good place to start. After finishing, you should take wonderful course [Introduction to Computer Science and Programming Using Python by MITx](https://www.edx.org/course/introduction-to-computer-science-and-programming-7).

Your suggestions are welcome at any time. Please contact me at pr.rahulpatel at gmail.com
