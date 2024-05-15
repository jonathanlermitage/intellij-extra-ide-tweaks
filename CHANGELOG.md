# Extra IDE Tweaks Change Log

## 2024.8.3 (planned for 2024/05/20)
* greatly improve the detection of `jcmd`, which is used to schedule GC on local JVMs.

## 2024.8.2 (2024/05/14)
* feature: you can **schedule GC on local JVMs**. May be useful when having multiple Gradle or Kotlin daemons consuming too much memory.
* add some missing Chinese translations.

## 2024.8.1 (2024/05/13)
* same features as 2024.8.2. Not published, because found some bugs in new features (now fixed in 2024.8.2). 

## 2024.7.1 (2024/04/17)
* **Better Folder Icons**: add more folder icons, and rework the Module folder icon color when using the regular UI in light mode.
* **Open In** actions: you can now open files with Associated Application. This additional action is enabled for IDEs prior to 2024 only, as it is already implemented by 2024+ IDEs.
* feature: you can **open projects located in trusted locations directly via File > Trusted Locations**. You no longer need to select File > Open, then find projects location via the operating system's file manager.
* fix usage of some JetBrains deprecated APIs.

## 2024.6.1 (2024/04/03)
* feature: can make folder icons more visible (with no outline style) when using the New UI. You can also use this feature with the regular UI. Takes effect after IDE restart.

## 2024.5.1 (2024/03/29)
* provide Chinese UI (based on DeepL). This is automatically applied if you enable the official IDE [Chinese Language Pack](https://plugins.jetbrains.com/plugin/13710-chinese-simplified-language-pack----) plugin.
* minor UI fixes.

## 2024.4.1 (2024/03/25)
* feature: can confirm the opening of specific files. May be useful when streaming and/or accidentally opening a sensitive file in situations where you can leak critical information.

## 2024.3.1 (2024/03/21)
* feature: you can register any program and add it to the "Open In" list when doing a right-click on a file, a folder, or a project. Your program will be added next to the "Open In" *Terminal* action. That means you can open files with your favorite program (like ForkLift...). You can register up to 2 "Open In" actions. Go to Extra IDE Tweaks settings for details.

## 2024.2.1 (2024/03/18)
* feature: the Open Editors tool window can also show recently opened files. It returns the same files list as the "Recent Files" action. Please note rendering of this files list is not perfect when using the New UI. You may face occasional `NullPointerException: Cannot invoke "javax.swing.CellRendererPane.paintComponent(...)" because "this.rendererPane" is null` warnings, but they break nothing. I will do my best to rework this in a future update.
* minor UI fixes.
* minor code reworks.

## 2024.1.2 (2024/03/15)
* rework the Open Editors tool window icon when using the New UI.
* fix a possible NPE when trying to fetch file icon in the Open Editors tool window.
* mitigate some "Slow operations are prohibited on EDT" warnings when using an EAP IDE.
* minor UI fixes.
* minor code reworks.

## 2024.1.1 (2024/03/13)
* feature: the **Open Editors** tool window shows opened files in all editors belonging to the opened project, as in VSCode.
* feature: you can **purge IDE's plugin download cache**.
* feature: you can **change most tool windows label**. Per example, rename the "Pull Requests" tool window to "PR".
* feature: add a menu item under *Tools* in order to **open the Plugins Manager directly**.
* feature: apply a **workaround for [IDEA-341174](https://youtrack.jetbrains.com/issue/IDEA-341174/Wrong-label-for-the-Git-toolwindow)**: the Git tool window may display the wrong label "Version Control" instead of "Git". This workaround is loaded 4s after project opening, then it updates the tool window label if your project has a ".git" sub-folder.

<!--* important rework of the Open Editors tool window, fixing some annoying issues like `NullPointerException: Cannot invoke (...) because "this.(...)" is null`.-->
