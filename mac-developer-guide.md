### Dev Setup in my Mac
### OS : BigSur

#### Installing Homebrew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Installing nvm using homebrew
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
