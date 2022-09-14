## A virtual environment in Powershell.

The virtual environment is used to create an isolated environment for the different projects. This helps developers to keep the dependencies required by projects separate. So let's learn basic commands to create and activate the virtual env and install packages on it.

#### Prerequisites,
- Python
- PIP

Install ```virtualenv``` package using the following command,

```
python -m pip install --user virtualenv
``` 
Now go to the folder where you want to create a virtual environment and run the following command to create a virtual environment with the name "env". This will create the folder named "env" in a directory.

```
python -m venv env
``` 

> You can name it whatever you what just make it logical and relative to your project.

To activate the virtual environment, go to the directory where you installed it and run the following command by replacing "env" with your environment name.

```
env\Scripts\activate
``` 
To install any package make sure the virtual environment is active. Use the following command to install the package.

```
pip install package-name
``` 
To install multiple packages use a comma ```,``` to separate package names. For example,

```
pip install requests, Django, BeautifulSoup
``` 
To install packages using ```requirements.txt``` file, use the following command
```
pip install -r requirements.txt
```
To get package names installed on a virtual environment into a ```requirements.txt``` file use the following command.
```
pip freeze > requirements.txt
```
To deactivate the env use,
```
deactivate
```

I am a total beginner and may have missed command that I never used before. So, please comment below few commands that are helpful for developers. Thanks for reading and do follow for more such articles.


> Never stop learning!
