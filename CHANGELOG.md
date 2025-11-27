# Extra IDE Tweaks Change Log

## 2025.1.16 (WIP)
* the minimal IDE version is now 2025.1.
* UI reworks in the plugin's settings panel.
* implement [#7](https://github.com/jonathanlermitage/intellij-extra-ide-tweaks/issues/7): provide an assistant to find (via regular expressions) and register multiple entries to add to the `Always Excluded Folders` list.

## 2025.1.15 (2025/11/21)
* this release adds compatibility with Huawei DevEco Studio and has been tested with DevEco Studio 5.1.1 (I don't have access to DevEco Studio 6 yet, but it should work). [See how to install plugin and activate your license in DevEco Studio](https://jonathanlermitage.github.io/ij-extra-tools-pack-docs/deveco-studio.html).
* support more older IDEs. The minimal IDE version is now 2023.3 (previously 2024.3).
* **highly recommended update**: prevent a potential IDE freeze when the `Always Excluded Folders` feature is enabled and the IDE is opening a very large project or many smaller projects that need a complete re-indexing, and too many modules are present. This is an improvement of the original fix provided in the 2025.1.12 (2025/08/27) plugin release. The `Always Excluded Folders` was disabled for projects with more than 20 modules, but the IDE may also invoke this function by passing the modules one by one. Per example, with a project with 1600 modules (like the IntelliJ Community sources), it invoked the function with the 1600 modules, so I blocked it, but just after that, it also invoked the function 1600 times, one time for each module, which may freeze the IDE for a long time. This is now fixed by caching (in memory) the number of modules for the opened project. Also, this fix and other reworks allows me to increase the maximum number of modules from 20 to 100.

## 2025.1.14 (2025/10/16)
* fix usage of some JetBrains deprecated APIs, improving the compatibility with future IDEs (2025.3+).

## 2025.1.13 (2025/10/08)
* fix usage of some JetBrains deprecated APIs, improving the compatibility with future IDEs (2025.3+).

## 2025.1.12 (2025/08/27)
* prevent a potential IDE freeze when the `Always Excluded Folders` feature is enabled and the IDE is opening a very large project or many smaller projects that need a complete re-indexing.

## 2025.1.11 (2025/08/05)
* new series of workarounds for the [IDEA-376370](https://youtrack.jetbrains.com/issue/IDEA-376370/) issue. Up-voting this issue would greatly help.

## 2025.1.10 (2025/07/30)
* workaround for the [IDEA-376370](https://youtrack.jetbrains.com/issue/IDEA-376370/) issue.

## 2025.1.9 (2025/07/11)
* new fix for `SettingsService is in unnamed module of loader com.intellij.ide.plugins.cl.PluginClassLoader` errors.

## 2025.1.8 (2025/07/01)
* fix the **purge IDE's plugin download cache** feature. Archive files for installed plugins no longer required by the IDE were not deleted.

## 2025.1.7 (2025/06/27)
* fix potential `SettingsServiceB is in unnamed module of loader com.intellij.ide.plugins.cl.PluginClassLoader` errors.
* improve the **purge IDE's plugin download cache** feature. Pending plugin installs and updates are no longer affected.

## 2025.1.6 (2025/06/13)
* the minimal IDE version is now 2024.3 instead of 2023.3.1. This was needed to use newer JetBrains APIs and stay compatible with future IDEs (2025.2+).
* fix usage of some JetBrains deprecated APIs, improving the compatibility with future IDEs (2025.2+).
* the **Commit Alert** feature now ignores some common files like media files (pictures and videos, PDF files, Office files, etc.), archives, and binary files. This will greatly improve the performance when committing these files. A future update will let you configure this.

## 2025.1.5 (2025/05/06)
* fix for error `Class initialization must not depend on services. Consider using instance of the service on-demand instead`.

## 2025.1.4 (2025/04/14)
* UI fixes in the plugin's settings panel.

## 2025.1.3 (2025/03/17)
* settings can now be loaded and saved by the **Backup and Sync** plugin.
* prevent a `Slow operations are prohibited on EDT` warning on project loading with IntelliJ 2025.1 EAP when the `Always Excluded Folders` feature is enabled.
* various code reworks.

## 2025.1.2 (2025/02/25)
* improve the plugin's compatibility range. The minimal IDE version is now 2023.3.1 instead of 2024.1.

## 2025.1.1 (2025/01/21)
* disable the `Always Excluded Folders` feature when loading projects with a huge number of modules (like IntelliJ Community sources, which has 1300 modules). The module limit is set to 20 to avoid any performance degradation. A future update will rework this feature.
* rework the `Open Editors` tool window icon.
* improve the search field at the top of the config panel. This should work much better.
* rework how the Chinese language is detected. This should avoid rare scenarios where the Chinese localization of the plugin was loaded on non-Chinese computers. 
* minor code rework.
* rework how the Chinese language is detected. This should avoid rare scenarios where the Chinese localization of the plugin was loaded on non-Chinese computers.
* [documentation](https://jonathanlermitage.github.io/ij-extra-tools-pack-docs/extra-ide-tweaks.html).

## 2024.18.1 (2024/12/13)
* **Better Folder Icons** now supports the `(.)log(s)` folders from Extra Icons.
* **Prevent Opening of Sensitive Files** now supports read-only files (2024.2+ IDEs only).

## 2024.17.2 (2024/11/19)
* hopefully fix `com.intellij.diagnostic.PluginException: Cannot init component state (...)` errors.
* fix a potential licensing issue introduced by the previous plugin version.

## 2024.17.1 (2024/11/16)
* **Properties** context menu: display file or folder properties (like size, number of files, etc.).

## 2024.16.2 (2024/10/29)
* fix potential component ID collisions when installing this plugin alongside other obfuscated plugins.
* code rework: replace usage of obsolete JetBrains APIs, improving compatibility with future IDEs.

## 2024.16.1 (2024/10/21)
* **Better Folder Icons** now supports the Kotlin Multiplatform OS folders from Extra Icons.
* add **Commit Alert**: this inspection allows you to define keywords that will show a confirmation dialog before committing files containing any of those keywords. Per example, define the COMMIT_ALERT keyword, modify, delete or move one or multiple files containing it, then commit. A confirmation dialog will appear asking if you still want to commit.
* add **Activate All Tool Windows**: this action activates all available tool windows in the current project. Enable it in settings, then see the `Window > Activate All Tool Windows` menu item. It's like clicking on the "..." button on the left-side toolbar, then clicking on each available tool window.
* add options to show `Tools > Extra IDE Tweaks...` and `Tools > Plugins...` menu items.
* settings: a search field has been added for quicker access to the parameters you are looking for.
* minor UI reworks in the settings panel.
* minor performance optimization.

## 2024.15.2 (2024/09/23)
* fix usage of some JetBrains deprecated APIs, improving the compatibility with future IDEs (2024.3+).
* rework the `Prevent Opening of Sensitive Files` feature. Because there is no official API for that, I was using a workaround, but recent IDE updates made it less reliable, making (sometimes) the file content visible during a brief instant. I found new workarounds that work with most IDE installations. BTW, these are still workarounds, and up-voting [IDEA-359327](https://youtrack.jetbrains.com/issue/IDEA-359327/Provide-an-API-to-prevent-file-opening) would greatly help.
* reduce the plugin size by removing the dependency to Apache Commons IO and by using custom code from Java NIO instead.

## 2024.15.1 (2024/09/17)
* improve compatibility with future IDEs (2024.3+).
* add **Open as Project** to the folder's context menu from the Project tool window. The idea is to implement [IJPL-158161](https://youtrack.jetbrains.com/issue/IJPL-158161).
* add the ability to have **default Excluded Folders** from indexing. There is now a global list of excluded folders. The idea is to implement [IJPL-8363](https://youtrack.jetbrains.com/issue/IJPL-8363).
* **Better Tab Names**: add an option to remove the parenthesis after the file name if it's located in the root project or module. Per example, renames "build.gradle.kts (my-module)" to "build.gradle.kts". For now, it works with "build.gradle", "build.gradle.kts", "build.gradle.dcl", "settings.gradle", "settings.gradle.kts", "settings.gradle.dcl" and "src/main/resources/META-INF/plugin.xml" files only.
* minor code rework.

## 2024.14.1 (2024/08/27)
* improve compatibility when the Python plugin (Ultimate or Community) is installed.
* **Better Folder Icons**: add an icon for Python projects.
* make the `Tools > Extra IDE Tweaks...` and `Tools > Plugins...` menu items available while indexing.
* improve translations: replace "regular UI" with "classic UI".

## 2024.13.1 (2024/08/20)
* fix [#2](https://github.com/jonathanlermitage/intellij-extra-ide-tweaks/issues/2): `Prevent Opening of Sensitive Files` is broken in 2024.2+ IDEs.
* avoid an invisible error when closing a project or the IDE. This error had no impact other than to pollute the IDE logs.
* add an option to disable the plugin's features. Use it if you installed Extra Tools pack, but you don't want Extra IDE Tweaks features.
* add an option to disable the Open Editors tool window.
* improve translations.
* translate the `Trusted Locations` and `Favorite Projects` menus in Chinese.

## 2024.12.1 (2024/07/21)
* the **Open Editors** tool window is now using [JetBrains' Tree](https://plugins.jetbrains.com/docs/intellij/lists-and-trees.html#jblist-and-tree) implementation instead of JTree, leading to some benefits like a better UI. Drawing a tooltip with complete text of an item if the item doesn't fit into the list box width. It also integrates the **Speed Search** functionality, [similar to Speed Search for Tool Windows](https://www.jetbrains.com/help/idea/speed-search-in-the-tool-windows.html): type text when the Open Editors tool window has focus, and the selection moves to the first item that matches the specified string.
* fix `Slow operations are prohibited on EDT` issues when using the Open Editors tool window in an EAP IDE.
* minor performance improvements.
* fix a license detection [issue](https://github.com/jonathanlermitage/ij-extra-all-plugins-pack-pub/issues/1).

## 2024.11.1 (2024/07/08)
* make the `File > Favorite Projects` and `File > Trusted Locations` menus available during indexing.
* Favorite Projects: add a menu item to re-open favorite projects while preserving their order of registration. Useful if you're in the habit of opening several projects systematically in the same order.
* improve Tool Windows Label Override: reapply user's rules if the IDE has reverted to a tool window label (it can happen when enabling AI Assistant).
* minor performance improvements and enable future performance improvements for 2024+ IDEs (based on JBR21).
* general stability improvements. Some internal concurrent components were not ideally synchronized, which could lead to minor performance degradations. This is now fixed.

## 2024.10.1 (2024/06/26)
* feature: **Favorite Projects**. Go to settings and add projects to favorites, organize them with groups, and gain fast access to your favorite projects via `File > Favorite Projects`.
* settings: table lines can now be reordered.
* settings: fix NPE when adding empty lines in tables.
* `File > Trusted Locations`: visual and performance improvements.

## 2024.9.2 (2024/06/21)
* 2024.2 IDEs now bundle the Chinese Language Pack plugin. For these IDEs, plugin's Chinese UI is now applied only if you select the Chinese locale (File > Appearance & Behavior > System Settings > Language and Region). For older IDEs, plugin's Chinese UI is applied if you download and enable the Chinese Language Pack plugin.
* minor code and UI rework.

## 2024.9.1 (2024/06/15)
* replace the plugin's custom error reporter by the new IDE [Exception Analyzer](https://plugins.jetbrains.com/docs/marketplace/exception-analyzer.html). This is an easy way to report plugin exceptions from IntelliJ Platform-based products to plugin developers right on JetBrains Marketplace, instead of opening an issue on the plugin's GitHub repository.
* schedule GC on local JVMs: kill `jcmd` processes spawned by plugin if they are not responding. This can happen when `jcmd` processes are executed when your computer wakes up from sleep/hibernation.

## 2024.8.7 (2024/06/10)
* `File > Trusted Locations` can now also display projects in first-level subdirectories. Disabled by default, you can enable this in settings.
* improve the performance of `File > Trusted Locations` and run it in a background task. The list of projects found is computed at IDE start then it's cached until next IDE start, or if you refresh it by going to `File > Trusted Locations > Refresh from Disk`.
* minor code and UI rework.

## 2024.8.6 (2024/06/03)
* minor code rework.

## 2024.8.5 (2024/05/30)
* schedule GC on local JVMs: avoid infinite progress bar when `jcmd` (invoked to run GC on local JVMs) hangs, and kill it if needed.

## 2024.8.4 (2024/05/27)
* fix an issue preventing from opening sensitive file when no other file is already opened in editor, even when user asks to open given sensitive file.

## 2024.8.3 (2024/05/22)
* greatly improve the detection of `jcmd`, which is used to schedule GC on local JVMs.
* schedule GC on local JVMs: add JetBrains' Remote Maven Server to the default list of JVMs.
* internal: migrate to IntelliJ Platform Gradle Plugin v2, ensuring build compatibility with 2024.2+ IDEs.

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
