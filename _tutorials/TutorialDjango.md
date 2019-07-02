---
layout: tutorial
title: Docker for Django tutorial
---
# Create basic static-website by using docker 

A static website contains Web pages with fixed content. Each page is coded in HTML and displays the same information to every visitor. Static sites are the most basic type of website and are the easiest to create. Do not require any Web programming or database design. A static site can be built by simply creating a few HTML pages and publishing them to a Web server.

### Prerequisite
- You have to install one of the docker programs. In window 10 PRO and window 10 Education will using Docker desktop, another window will using docker toolbox for implemented website.
- Install a necessary program to your computer(Text editor,Git,Python).
- Make sure that your text editor program can use to implemented powershell(.ps1) if you can't edit the powershell download it in extension part of your editor. Suggest to use visual studio code to easy edit the code.
- You have to have a basic knowledge about docker, what is docker?, what docker composed of?
- For those who using docker toolbox you can using docker toolbox shell
- Have Basic knowledge about the virtual environment and python

# Set up Environment 

## Start developed program

1.Install virtualenv

- Using python for install virtualenv. Virtualenv or also called Virtual Environment used to seperate environment for each workspace.When you work in many project at one time , you have to use each python library for each workspace. But when you install many version of python library , your computer will be complicated and mess. So, to solve this problem their used virtualenv to seperate all environment from each other.
- **`Virtualenvwrapper`** is a script that help you to easily used virtualenv. Example likes a users want to create a new environment, and start to use this environment. User can be use in shortly than type command for new python library versioon about 2-3 command. User use just one shortcut command of virtualenvwrapper and then done.
- To install virtualenv it consist of 3 steps

    1.1 Make sure that you already have **`easy_install`** in your computer.

    1.2 **`easy_install pip`**.
    
    1.3 **`pip install virtualenv`**.

2.This command will be run on Window Powershell or Window Powershell run as adminstrative user not ISE, normal command prompt or doccker quickstart shell for install Django(The Web framework for perfectionists with deadlines)

{% raw %}
```
PS virtualenv myenv
PS Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
(myenv) PS .\myenv\Scripts\activate.ps1
(myenv) PS pip install django
```
{% endraw %}

- **`virtualenv myenv`** - create new environment called myenv
- **`.\myenv\Scripts\activate.ps1`** - This is command of virtualenvwrapper for activate environment to make it easy to use and get user to work inside the environment. When this already run in front of the line will be shown (env name)
- **`Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`** - Set policy in powershell that can make and determine the scripts of powershell can be run on the system. 
- **`pip install django`** - to install django by using python language.

![Env](/assets/env1st.jpg)

3.Install MysqlClient by using python version to download example likes you use python version 3.7 (check python version **`python --version`** by you have to download Mysqlclient cp37. [Click](: https://www.lfd.uci.edu/~gohlke/pythonlibs/#mysql-python) and install by using command cd to go to file cp37 directory like **`download`** then **`pip install filename`**

- Make sure for the version and windows system type of your computer whether its 32-bits or 64-bits.
- Note: However your computer is 64-bits but you have to download mysqlclient 32-bit if you download python 32-bits. Make sure for the version of python if it 64-bits,you download 64-bits mysqlclient the same version.
{% raw %}
```
(myenv) PS cd .. //go to path that keep file mysqlclient
(myenv) PS pip install .\mysqlclient-1.4.2-cp37-cp37m-win_amd64.whl //if you use python version 3.7 64-bits
```
{% endraw %}

- Check your computer system type

![Windowcheck](/assets/windowcheck3264.jpg)

- Choose to download mysqlclient the same version and bits as python program

![MysqlClient](/assets/mysql1st.jpg)

- Type in Powershell with already run environment

![Mysqlcommand](/assets/mysql2nd.jpg)
 
# Django
4.Create Python Django Project and Run Server
{% raw %}
```
(myenv) PS django-admin startproject mysite
(myenv) PS cd mysite
(myenv) PS python manage.py runserver
```
{% endraw %}
![Django](/assets/django.jpg)
- [check out http://127.0.0.1:8000/ ](http://127.0.0.1:8000/)

![Django](/assets/mysql4th.jpg)

# When Restart or close command prompt 

When you are already done everything, you doesn't want to go back and do it again when you shut down, restart or close the command prompt. You open your computer and then using PowerShell and then run with Administartor mode and then run environment again. You have to go to your directory path of your file then run environment.
- Note: that for running environment file you should run  **`.\env.bat `** too, For command prompt. For PowerShell, you have to change  **`.\env.ps1 `** (ps1: Powershell Script)
- Run all of this command and then you can use this environment

{% raw %}
```
PS Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS .\myenv\Scripts\activate
(myenv) PS env.bat (env.ps1) // if you run in powershell you have to run `.\env.ps1`
```
{% endraw %}

![Admin Run again](/assets/Adminrun.jpg)
