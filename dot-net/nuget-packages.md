# NuGet Packages

## Download Behavior

__Background:__ With recent additions to our nuget packages, we have noticed that they seem to break when a user uses a computer for the first time, or there is a new cloning of the repository. They say they are installed, but during compile time, they show as missing.

__Why this happens:__ This is actually an expected behavior for NuGet... NuGet resotres files in the packages directory (\packages folder), but does not restore files inside your project or otherwise modify the project. (Source: [GitHub](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet))

__Solution__: Reinstall all of your NuGet packages by hand to fix the problem, or simply type `Update-Package -reinstall` into the NuGet terminal in visual studio. With experiementation, sometimes it shows all of the .dll files as changes in git. Feel free to reset and remove those changes. The new package install should still work. (At least it did on the 1 pc we tried it on lol.)
