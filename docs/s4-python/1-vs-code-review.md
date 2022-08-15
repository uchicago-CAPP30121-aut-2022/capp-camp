---
layout: default
title: VS Code Review
nav_order: 1
parent: Python Programming
---

# VS Code Review

Recall from the [first lab](../s1-linux/index.md) the main components of VS Code's graphical interface: 

- **Editor**: The main section of the application, where files are edited. Defaults to a "Getting Started" file when you first launch the application if you haven't opened any files for editing yet.

- **Menu Bar**: The horizontal bar at the top of the application. Provides sub-menus allowing you to quickly open your workspace to a new file or folder, save files, and launch new terminals.

- **Activity Bar**: The vertical bar on the lefthand side of the application. Has buttons for the file navigation, file search, Git source control, debugging, and extensions, among others.

- **Status Bar**: The horizontal bar at the bottom of the application. Shows the number of current code warnings and errors as well as the line number and file type of the file that is currently active in the Editor.

- **Terminal**: A panel that opens underneath or to the side of the Editor. Defaults to the `bash` shell. Allows you to navigate folder directories and execute commands.

In this section, we'll dive deeper into general features of VS Code that allow us to program more efficiently.

## Manipulating Terminals

To open a new terminal, select "Terminal > New Terminal" on the Menu Bar.  The terminal that appears will open to the default shell (i.e., `bash` for Linux). You can also see the terminal listed according to its shell name on the righthand side of the terminal panel.

In the future, you might want to use multiple terminals simultaneously, perhaps even of different shells. Try out this feature by clicking the "+" button on the righthand side the terminal to open another terminal of the default shell type. Then click the dropdown arrow next to the "+" button to open a new terminal with a specific shell type. As you add new terminals, their names also appear in the righthand panel.

VS Code also allows users to split one terminal into multiple views. To test out this feature, right click on one of the terminals you have created and select "Split Terminal". Now two terminals are open to the same directory, and their names have a connection line drawn between them.

To remove terminals, simply hover over their name and click the trash can icon that appears.  When all terminals are gone, the terminal panel disappears so only the editor is displayed. To toggle the terminal panel open and closed, so it is displayed or  hidden, you can use the shortcut `Ctrl+\``.  If there are no terminals open when the terminal panel is toggled open, a new one open to the default shell will be displayed.

## Manipulating Editor Tabs

As we discussed in the first lab, you can open a new file in VS Code's Editor by running the keyboard shortcut `code <filename>` in the terminal. You can also select a file manually through the Explorer Menu on the Activity Bar or by using `Ctrl-P` and searching for the file in the workspace.

To view two files side by side, simply drag and drop the file to the desired position in the window. You'll see highlighted options available (i.e., right side, left side, top, bottom) as you move around.

You can also view the same file side-by-side by right-clicking its Editor tab and then selecting one of the split options: `Split Up`, `Split Down`, `Split Right`, `Split Left`. This will generate a new view of the same file. Edits made to one will immediately be shown in the other. If you close one, the other remains open. This functionality is highly useful for viewing assignment directions or a section of code being used as a reference on one side of the application and the code you're actively writing, on the other side.

To close a file, simply hover over its Editor tab and click the "x" button. You can also right-click its tab and select "Close".

## Changing Application Appearance

VS Code's appearance can be adjusted for preference and to ensure accessibility for all users.

- **Color**: To change the color theme, click on the Manage button in the Activity Bar (i.e., the gear at the bottom) and then select "Color Theme".  The application defaults to "Dark+", but you can choose from among other built-in light, dark, and high-contrast options. You can also select "+ Browse Additional Color Themes" to search the VS Code marketplace for themes submitted by community members. Those with color vision deficiency can search the marketplace for color blind options. Microsoft  recommends "GitHub", "Gotthard", "Blinds", or "Greative" as choices.

- **Zoom**: To increase font size across the application, you can zoom in using "View > Appearance > Zoom In" on the Menu Bar or simply use the keyboard shortcut `Ctrl+=`. The default zoom is 0, and each increase in zoom level results in a 20 perent increase.  You can similarly zoom out using "View > Appearance > Zoom Out" on the menu bar or `Ctrl+-`.  This zoom level is persisted in VS Code (through the `window.zoomLevel` setting) until it is changed again.

For more ways of configuring VS Code for greater accessiblity, please visit [this page](https://code.visualstudio.com/docs/editor/accessibility) on the official website.

## Turning on Auto-Save

By default, VS Code requires users to explicitly save their changes to the disk by using the keyboard shortcut `Ctrl+S` or by navigating to the Menu Bar and selecting "File > Save". However, if you would like VS Code to automatically save changes for you, you can turn on this setting by selecting "File > Auto Save". By default, the setting will save new changes every second. However, you can configure the setting to occur following a different condition:

- `off` - Auto-save disabled. (Default)

- `afterDelay` - Saves files after a configured delay. (Default when auto-save is turned on from the Menu Bar.)

- `onFocusChange` - Saves changes after your focus leaves the file's tab within the Editor.

- `onWindowChange` - Saves changes after your focus leaves the VS Code window.

- `files.autoSaveDelay` - Configures the delay in milliseconds when `afterDelay` is selected. Defaults to 1000.

To alter the Auto Save settings, click on the Manage button and then select "Settings".  Alternatively, you can use the keyboard shortcut CTRL followed by comma: `Ctrl+,`.  Search for "Auto Save" and then make changes in the panel that appears.