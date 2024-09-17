# Installation with Apt

Check if java is installed:
```sh
java -version
```

If not, first install JRE:
```sh
sudo apt update
sudo apt install default-jre
java -version
```

Then install JDK:
```sh
sudo apt install default-jdk
javac -version
```

Set JAVA_HOME path:
Get path where java is installed:
```sh
sudo update-alternatives --config java
```
You should get like:
```
Il n'existe qu'une « alternative » dans le groupe de liens java (qui fournit /usr/bin/java) : /usr/lib/jvm/java-11-openjdk-amd64/bin/java
Rien à configurer.
```
Copy path without `/bin/java`and add it in .profile:
```
echo "/usr/lib/jvm/java-11-openjdk-amd64" >> ~/.profile
source ~/.profile
```


