# Pyenv

```sh
#Install a new version ⚠️ It doesn't set it as current
pyenv install <python_version>
#Uninstall python version
pyenv uninstall <python_version>
```

```sh
#Select python version only for shell version
pyenv shell <python_version>
#Select python version only for the current dir and its subdir
pyenv local <python_version>
#Select python version globally
pyenv global <python_version>
```

# Virtual envrionment

```sh
#Go to the directory where you want to create the venv
cd <my_dir>
#Then select the version you want (global work for sure) with pyenv
#Check the version is good
python --version
#Create the venv
python -m venv <venv_name>
```

# PIP
```sh
#Install module listed in requirements.txt
pip install -r requirements.txt
#Remove all module installed 
pip freeze | cut -d "@" -f1 | xargs pip uninstall -y
```

# Openpyxl

```
wb = Workbook()

ws = wb.active
ws.append(aList)

wb.save(<nameOfFile>)
```
