
# sls
Simple Logging System

## What ChatGPT made for me

SLS, or the Simple Logging System, is a software tool created by a programmer named VTF. The inspiration for this tool came from VTF's ADHD-driven thoughts and ideas, which led to the creation of a unique and innovative software tool.

SLS is designed to simplify the logging process by creating files and organizing data in a clear and concise manner. It is not limited to any specific programming language but can be used with a wide range of languages, making it an incredibly versatile tool for developers of all backgrounds and skill levels.

Unlike other logging systems, SLS focuses on creating a user-friendly interface that makes it easy for programmers to track their code's performance and monitor any errors or issues that may arise. It does this by generating log files that provide detailed information about each request, including the date and time of the request, the type of request, and any error messages that may have been encountered.

One of the unique features of SLS is its ability to create custom log files for each application or project. This means that developers can easily keep track of multiple applications or projects and quickly locate any issues that may arise without having to sort through a massive log file.

Despite being an ADHD idea, VTF has put a lot of effort into making SLS a functional and reliable tool. While it is still in the early stages of development, VTF is optimistic about its potential and hopes that it will gain some success in the developer community.

Overall, SLS is an exciting and promising software tool that has the potential to revolutionize the way developers approach logging. Its versatility, user-friendliness, and customizable features make it an invaluable asset to any development team looking to streamline their logging process and optimize their code's performance.

## I have no idea what CGPT did so lemme explain in short
sls was a stupid idea for logging text into files with timestamps. god knows why i did it but i hope with works with other people.

Heres the code bcuz:

```python
# TODO add the following to the menu:
#   #######################
#   # File handling flags #
#   #######################
#   
#       -t      handle as a text (e.g: c -t customerlogs.log)
#       -b      handle as binary (e.g: c -b customerlogs.log)

# TODO: add a folder system as per requested
#i'on even know
import socket as skt
from datetime import datetime
from time import sleep
import os
import shutil

#simple info for people who use this on a SSH or anything.
machineName = skt.gethostname()
machineIP = skt.gethostbyname(machineName)

# date adn time for logging
currentTime = str(datetime.now())

print(f'Your machine`s name is "{machineName}" and your IP is "{machineIP}"\n\n\n')

#main
sleep(2)

#prints a menu, for selecting modes and flags
print('''

simple logging system,

                        by bergua sensua
       
         for general purpose

                           or whatever you want!


Select option.
#####################


File related
    c       create a file (e.g: c customerlogs.log)
    cff     check if a certain file exists (e.g: cff customerlogs.log)
    r       read a file (e.g: r customerlogs.log)
    a       append text to a bottom of a file (e.g: a customerlogs.log)      
    w       write to the file (e.g: w customerlogs.log) [THIS WILL REMOVE PREVIOUS CONTENTS]
    d       delete a file (e.g: d useless.log)
  
Folder Related
    gcwd    get the current directory you are in.
    o       open a folder
    nf      create a folder
    cf      check if a folder exists
    nfif    create a file in a folder
    rf      rename folder
    df      delete a folder

''')

cwd = os.getcwd()
print(f'Your current directory is \'{cwd}\'')


while True:
    userMenuInput = str(input()) # is for modes

    mode = userMenuInput

    if mode == 'c':
        fileToCreate = str(input('What should the file be called? (This should include the extension, like logs.log or my.extension\n'))
        file = open(f'{fileToCreate}', 'x')
        file.close()

    elif mode == 'cff':
        fileToCheck = str(input("What file are you looking for?\n"))
        checkedFile = os.path.exists(f'{fileToCheck}')
        if checkedFile == True:
            print(f'{fileToCheck} exists.')
        else: 
            print(f'{fileToCheck} Doesn`t exist')

    elif mode == 'r':
        fileName = str(input('Insert file name.\n'))
        file = open(f'{fileName}', 'rt')
        print(file.read())
        file.close()

    elif mode == 'a':
        fileName = str(input('Insert file name.\n'))
        toAppend = str(input('Insert text.\n'))
        file = open(f'{fileName}', 'a')
        file.write('\n' + currentTime + ' || ' + toAppend)
        file.close()

    elif mode == 'w':
        fileName = str(input('Insert file name.\n'))
        file = open(f'{fileName}', 'w')
        toWrite = str(input('Insert Text.\n'))
        file.write(currentTime + ' || ' + toWrite)
        file.close()

    elif mode == 'd':
        fileName = str(input('Insert file name.\n'))
        os.remove(fileName)

    elif mode == 'nf':
        makeDir = str(input('What shall the folder be named?\n'))
        os.mkdir(makeDir)

    elif mode == 'cf':
        checkDir = str(input('What is the name of the folder? \n'))
        check = os.path.exists(checkDir)
        if checkDir == True:
            print(f'{checkDir} exists.')
        else:
            print(f'{checkDir} doesn`t exist.')

    elif mode == 'nfif':
        cwd = str(input('What is the name of the folder? (if its a folder within a folder do customerdata\\geroge)\n'))
        os.chdir(cwd)
        fileToCreate = str(input('What should the file be called? (This should include the extension, like logs.log or my.extension\n'))
        file = open(f'{fileToCreate}', 'x')
        file.close()
    
    elif mode == "rf":
        toChange = str(input('What is the name of the folder? (if its a folder within a folder do customerdata\\geroge)\n'))
        newName = str(input('What shall the new name for the folder be?\n'))
        os.rename(toChange, newName)

    elif mode == 'df':
        toDelete = str(input('What is the name of the folder? (if its a folder within a folder do customerdata\\geroge)\n'))
        shutil.rmtree(toDelete)
    
    elif mode == 'gcwd':
        print(cwd)
        
    else:
        print('Thats not a mode, try again.')
        continue

    print('Would you like to use sls again?(y/n)')
    useAgain = str(input(''))
    if useAgain == 'y':
        print('''
Select option.
#####################


File related
    c       create a file (e.g: c customerlogs.log)
    cff     check if a certain file exists (e.g: cff customerlogs.log)
    r       read a file (e.g: r customerlogs.log)
    a       append text to a bottom of a file (e.g: a customerlogs.log)      
    w       write to the file (e.g: w customerlogs.log) [THIS WILL REMOVE PREVIOUS CONTENTS]
    d       delete a file (e.g: d useless.log)
  
Folder Related
    gcwd    get the current directory you are in.
    o       open a folder
    nf      create a folder
    cf      check if a folder exists
    nfif    create a file in a folder
    rf      rename folder
    df      delete a folder

        ''')
        continue
    elif useAgain == 'n':
        break
```
