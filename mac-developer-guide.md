## Dev Setup in my Mac
### OS : BigSur

### Installing Homebrew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Installing nvm using homebrew
```
brew update
brew install nvm
source $(brew --prefix nvm)/nvm.sh
```

Add the last command to the .profile, .bashrc or .zshrc file to not run it again on every terminal start. So for example to add it to the .profile run:
```
echo "source $(brew --prefix nvm)/nvm.sh" >> ~/.profile
echo "source $(brew --prefix nvm)/nvm.sh" >> ~/.bashrc
echo "source $(brew --prefix nvm)/nvm.sh" >> ~/.zshrc
```
To see what Node versions are available to install run:
```
nvm ls-remote
```
For me, I just needed the latest point release of Node version 11 so I ran
```
nvm install 11
```
After installing you can verify what is installed with
```
nvm ls
```
If you have multiple versions and you want to specify which version you would like to use, simply use:
```
nvm use 11
```
to use Node version 11.
Switching back to, let’s say, version 12 would be as easy as ```nvm use 12.```


### Installing Java 8

Navigate to [Oracle Site](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html) where all OS versions of Java JDK is present.

Choose macOS x64 version

Install the same in mac

Post installation run the following command to fetch 
```
$ /usr/libexec/java_home -V
```
Get the Java SE 8 Path in my case it was
```
/Library/Java/JavaVirtualMachines/jdk1.8.0_271.jdk/Contents/Home
```
Now lets Create a bash profile & open the same for editing :
```
$ touch ~/.bash_profile; open ~/.bash_profile
```
Now you have .bash_profile which is created in /Users/<user>/.bash_profile
Copy the given command and save the same into .bash_profile

```
export JAVA_HOME=$(/usr/libexec/java_home -v 1.8.0)
```
Now update the .bash_profile
```
$ source ~/.bash_profile
```
Verify the Java version by running ``` java -version```

Side Note : JRE is a part of JDK. You need not have to install JRE when you have JDK. If you open JDK folder, you'll have JRE folder inside it.

### Installing AEM
