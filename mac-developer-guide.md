## Dev Setup in my Mac
### OS : Catalina

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
echo "source $(brew --prefix nvm)/nvm.sh" >> ~/.bash_profile
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

### Switching between Java Versions

Navigate to [Oracle Site](https://www.oracle.com/java/technologies/javase/) where all OS versions of Java JDK is present.

Choose macOS x64 version and the java version (In our case lets choose Java11)

Install the same in mac

#### Switching versions

Add the following aliases to .bash_profile.
```
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_11_HOME=$(/usr/libexec/java_home -v11)

alias java8='export JAVA_HOME=$JAVA_8_HOME'
alias java11='export JAVA_HOME=$JAVA_11_HOME'

# default to Java 11
java11

```
Reload .bash_profile for the aliases to take effect.
```
$ source ~/.bash_profile
```
Use the alias to change version.
```
$ java8
$ java -version
java version "1.8.0_162"
Java(TM) SE Runtime Environment (build 1.8.0_162-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.162-b12, mixed mode)
```

### Installing AEM Instance in you Mac

Obtain the AEM Jar file as well as license file from your company of occupation or from Adobe.

Place it inside a folder, rename the Jar file as aem-author-p4502.jar.

Double-click the aem-author-p4502.jar file to install the Author instance. This will start the author instance, running on port 4502 on the local computer.

If this doesnt pan out create a script with following command

```
java -jar aem-author-p4502.jar
```
This will start the author instance, running on port 4502 on the local computer.

You might have to run the script everytime to start the local instance.

### Installing IntelliJ and integrating with local AEM instance

Install [Jetbrains Toolbox](https://www.jetbrains.com/toolbox-app/) (This would allow to downgrade your intelliJ if thirdparty plugins are failing)

Install IntelliJ Community Edition from the Jetbrains Toolbox

Now download vault cli from [https://repo1.maven.org/maven2/org/apache/jackrabbit/vault/vault-cli/] (https://repo1.maven.org/maven2/org/apache/jackrabbit/vault/vault-cli/) (Recently from AEM6.4 or 6.5, vault cli is not present in /crx-quickstart/opt path bydefault. Post installation , note down the path to where it was unzipped 

Open IntelliJ , click command + , to open preference , Navigate to plugins consequently search and download IntelliVault, Post installation, IntelliJ has to be restarted for the plugin to work. 

Post restarting, click command + , to open preference , Navigate to Tools , Click IntelliVault , now configure the Vault directory as follows
```
/Users/../../folder/vault-cli-3.4.6
```
Click Ok , Now you are good to go.
