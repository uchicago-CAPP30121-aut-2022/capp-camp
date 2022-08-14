---
layout: default
title: MacOS
nav_order: 3
parent: Pre-Installation
---

# MacOS

Follow the instructions below to install Visual Studio Code (VS Code) and an SSH (Secure Shell) client.

## VS Code

1. Go to Visual Studio Code's [home page](https://code.visualstudio.com/). You should see a blue button labeled "Download for Mac: Stable Build". Click this button to download.

![VS Code homepage screenshot - MacOS](../assets/img/install-code-mac-1.png)

2. When the download is complete, you will have a new application file called "Visual Studio Code". (You might instead have zip file, with a name like VSCode-darwin-stable.zip; in this case, open the file to unzip it, and the Visual Studio Code application file should appear.) Open a Finder window and navigate to Downloads. (It will likely be listed under "Favorites" in the left sidebar). Locate the file named "Visual Studio Code", and drag it on top of Applications in the left side bar. Now, you can find VSCode in your Applications folder, and can open it with a click.

![VS Code installer screenshot - MacOS](../assets/img/install-code-mac-2.png)

## SSH Client

1. An SSH client comes pre-installed. However, you should check that it works as expected before moving on. Press `Command-Space` to open Spotlight Search. Begin typing "Terminal", and click on the option when it appears:

![VS Code installer screenshot - MacOS](../assets/img/install-ssh-mac-1.png)

2. When the terminal opens, type `ssh` and confirm that a list of available options for the command is displayed.

## Remote-SSH and Python Extensions

1. At this point, VS Code should be among your installed applications. Open it. In the left sidebar, there is an icon consisting of four squares, with one square separated off from the other three. This is the icon for VSCode extensions. Click it to open the Extensions Panel (alternatively, you can press Command-Shift-X).

![Click extensions icon screenshot](../assets/img/install-ext-1.png)

2. Search for and install the extensions "Python (Microsoft)" and "Remote - SSH (Microsoft)". To do this, click in the search bar ("Search Extensions in Marketplace") and start typing the name of the extension. When it appears, make sure the name and publisher matches exactly, and click "Install".

![Python extension selected screenshot](../assets/img/install-ext-2.png)

![Remtoe SSH extension selected screenshot](../assets/img/install-ext-3.png)


## Next Steps

Installing this software brings us one step closer to utilizing university servers for coding assignments. We'll explain how to remotely connect to these servers using SSH and VS Code in our first session.