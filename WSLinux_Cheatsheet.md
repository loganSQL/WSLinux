# Windows Subsystem for Linux (WSL)

Microsoft Windows 10 : Native Linux command line tools based on Ubuntu, including bash, sed, awk, ruby, python etc

WSL requires fewer resources (CPU, memory, and storage) than a full virtual machine. WSL also allows you to run Linux command-line tools and apps alongside your Windows command-line, desktop and store apps, and to access your Windows files from within Linux. This enables you to use Windows apps and Linux command-line tools on the same set of files if you wish.

Advantage: cross-platform tools natively on Linux, and Powershell natively on Windows

## Commands
Get started 
```
wsl
```
Linux Distro
```
lsb_release -a 
```
Shell Profile
```
ls -latr
cat .bashrc
cat .profile
```

## File Systems
File Systems /mnt/drive_letter/
```
ll
ll /mnt/c/
```
One of the main limitations of using WSL is that changing Linux files with a Windows app or tool is not allowed.
However changing Windows files with a Linux app or tools is allowed.
One way to use a Windows file with a Linux app is to use an absolute path, e.g. 
```
/mnt/c/Users/<Windows User>/Documents/Projects/<filename>
```
However not all Linux apps or tools can access a file using /mnt. A solution is to create a symbolic link.
Windows directory: C:\Users\<Windows User>\Documents\Projects Note: This directory exist.
Linux directory: /home/<Linux User>/Projects Note: This directory does not exist.
```
ln -s "/mnt/c/Users/<Windows User>/Documents/Projects" /home/<Linux User>/Projects
```

Now in WSL you can access the Windows directory as /home/<Linux User>/Projects or a specific file as /home/<Linux User>/Projects/<filename>, and if in WSL the current directory is ~ then Projects/<filename>

### Linux Drive vs Windows Drive
Files under the Linux root (i.e. /) are controlled by the subsystem. This allows for Linux specific behavior including but is not limited to:
* Files which contain invalid Windows filename characters
* Symlinks created for non-admin users
* Changing file attributes through chmod and chown
* Support case sensitivity

Files in mounted drives are controlled by Windows and have the following behaviors:

* Support case sensitivity
* All permissions are set to best reflect the Windows permissions


## Links

* [CommandlineBlog](https://blogs.msdn.microsoft.com/commandline/) - Windows Command Line Tools For Developers
* [WSL](https://docs.microsoft.com/en-us/windows/wsl/about) - Windows Subsystem for Linux Documentation

