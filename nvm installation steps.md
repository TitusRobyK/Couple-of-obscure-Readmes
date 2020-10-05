### Why install NVM ?
When working with Node.js, you might encounter situations where you need to install multiple versions of the runtime.

For example, maybe you have the latest version of Node set up on your machine, yet the project you’re about to start working on requires an older version. Or maybe you’re upgrading an old Node project to a more modern version and it would be handy to be able to switch between the two while you make the transition.

Without a good tool, this would mean spending a lot of time and effort manually uninstalling and reinstalling Node versions and their global packages. Fortunately, there’s a better way!

Introducing nvm

nvm stands for Node Version Manager. As the name suggests, it helps you manage and switch between different Node versions with ease. It provides a command-line interface where you can install different versions with a single command, set a default, switch between them and much more.

### Here are the steps to install NVM 

#### NB : If you have prior Node Installed in your computer, Follow the following steps

#### How to remove Node.js from Windows:

- Take a deep breath.

- Run npm cache clean --force

- Uninstall from Programs & Features with the uninstaller.

- Reboot (or you probably can get away with killing all node-related processes from Task Manager).

- Look for these folders and remove them (and their contents) if any still exist. Depending on the version you installed, UAC settings, and CPU architecture, these may or may     not exist:

  - C:\Program Files (x86)\Nodejs
  - C:\Program Files\Nodejs
  - C:\Users\{User}\AppData\Roaming\npm (or %appdata%\npm)
  - C:\Users\{User}\AppData\Roaming\npm-cache (or %appdata%\npm-cache)
  - C:\Users\{User}\.npmrc (and possibly check for that without the . prefix too)
  - C:\Users\{User}\AppData\Local\Temp\npm-*
  - Check your %PATH% environment variable to ensure no references to Nodejs or npm exist.

- If it's still not uninstalled, type where node at the command prompt and you'll see where it resides -- delete that (and probably the parent directory) too.

- Reboot, for good measure.

- Open the [windows-nvm repository](https://github.com/coreybutler/nvm-windows#node-version-manager-nvm-for-windows) in your internet browser and select the Download Now link.

- Download the nvm-setup.zip file for the most recent release.

- Once downloaded, open the zip file, then open the nvm-setup.exe file.

- The Setup-NVM-for-Windows installation wizard will walk you through the setup steps, including choosing the directory where both nvm-windows and Node.js will be installed.

- Once the installation is complete. Open PowerShell and try using windows-nvm to list which versions of Node are currently installed (should be none at this point): nvm ls

- Install the current release of Node.js (for testing the newest feature improvements, but more likely to have issues than the LTS version): nvm install latest

- Install the latest stable LTS release of Node.js (recommended) by first looking up what the current LTS version number is with: nvm list available, then installing the LTS     version number with: nvm install <version> (replacing <version> with the number, ie: nvm install 12.14.0).

- List what versions of Node are installed: nvm ls ...now you should see the two versions that you just installed listed.

- After installing the Node.js version numbers you need, select the version that you would like to use by entering: nvm use <version> (replacing <version> with the number, ie:   nvm use 12.9.0).

- To change the version of Node.js you would like to use for a project, create a new project directory mkdir NodeTest, and enter the directory cd NodeTest, then enter nvm use     <version> replacing <version> with the version number you'd like to use (ie v10.16.3`).

- Verify which version of npm is installed with: npm --version, this version number will automatically change to whichever npm version is associated with your current version     of Node.js.
