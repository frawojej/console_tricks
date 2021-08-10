# C:\
### Let's start with all the folders and files in the C: "root" directory^:
| Name | Folder / File / Shortcut | Hidden | Protected operating system file |
| ----- | ----- | ----- | ----- |
| $GetCurrent | Folder | Yes | No |
| $RecycleBin | Folder | Yes | Yes |
| [Documents and Settings](#documents-and-settings) | Shortcut | Yes | Yes |
| Downloads | Folder | No | No |
| NVIDIA^ | Folder | No | No |
| PerfLogs | Folder | No | No |
| Program Files | Folder | No | No |
| Program FIles (x86) | Folder | No | No |
| Program Data | Folder | Yes | No |
| Recovery | Folder | Yes | Yes |
| System Volume Information | Folder | Yes | Yes |
| Users | Folder | No | No |
| Windows | Folder | No | No |
| xampp^ | Folder | No | No |
| hiberfil.sys | File | Yes | Yes |
| pagefile.sys | File | Yes | Yes |
| swapfile.sys | File | Yes | Yes |

> ^ note: these files / folders aren't on "clean" Windows machine, it's from my computer

> If you want to see the hidden files / filders you need to mark the `Hidden items` option in `View` tab in File Explorer

![mark hidden](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/mark_hiddens.png)

> Also, if you want to see the Protected operating system files / folders you have to unmark the `Hide protected operationg system files (Recommended)` option in `View` tab in `Folder options`

> It's in `View / Options`

![view options](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/view_options.png)
![unmark protected operating system files](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/unmark_protected_operationg_system_files.png)

## $GetCurrent

$GetCurrent is a folder which is created by Windows 10 upgrades.
It contains logs about the upgrade and the necessary and essential for the update.
After the update it leaves the data.
It should be usually deleted after update.
However, sometimes these files aren't deleted and could accumulate on disk.

Source: [https://www.computertechreviews.com/definition/getcurrent/](https://www.computertechreviews.com/definition/getcurrent/)

Good article: [https://superuser.com/questions/1322503/can-i-safely-delete-folder-getcurrent-in-windows-10](https://superuser.com/questions/1322503/can-i-safely-delete-folder-getcurrent-in-windows-10)

## $RecycleBin

$RecycleBin is a special folder. It stores metadata of deleted item's location.

Inside this folder there are special named folders starting with `SID`\*.

```
* SID - security identifier, is a number used to identify user, group, and computer accounts in Windows. They're created when the account is first made in Windows and no two SIDs on a computer are ever the same. The term security ID is sometimes used in place of SID or security identifier
```
Every folder name is a different user's SID.

#### How can I check my SID?

To check your SID just type:
```bat
wmic useraccount get name,sid
```
in your CMD console.

Let's create file called `File.txt`

![create File.txt](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/file_txt.png)

And now drag and drop it to Recycle Bin

![file inside recycle bin](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/file_txt_inside_recycle_bin.png)

No let's open `C:\$Recycle.Bin\` folder using WSL.

Go to my_SID folder.
And list files using `ls -lA`.

The most likely you'll see 3 files:
- one starting with `$I`
second starting with `$R`
and the third called `desktop.ini`
- the `$I` file contains metadata about deleted file (deletion time, path...).
- the `$R` file include data inside the file.

They get random file name to avoid name conflicts.<br>
The name is always $I/$R + 6 random characters.<br>
The deleted file's $I and $R names are the same.<br>
The extension of the $R/$I file determines the file type displayed in recycle bin.

<br>

The `$I` file consists of:

- File header, always `02 00 00 00 00 00 00 00`
- Deleted file size, also 8 bytes
- Deletion date, also 8 bytes
- File name length (how many bytes the file has), 4 bytes
- Original full path of file with original file name


Sources: [https://www.lifewire.com/what-is-an-sid-number-2626005](https://www.lifewire.com/what-is-an-sid-number-2626005)

YT: [https://youtu.be/jk8Io_cgYyY](https://youtu.be/jk8Io_cgYyY)

## Documents and Settings

It is historical folder used for example in Windows XP.<br>
In Windows 10 it doesn't really matter.<br>
If you want to open it it says `Access denied`<br>

According to Social Technet Microsoft: `Documents and settings is not a real folder. It is called a junction point and is used for legacy program interface.`
[Social Technet Microsoft](https://social.technet.microsoft.com/Forums/windows/en-US/df74d97f-a311-48fa-848f-5025540b53af/how-to-delete-cdocuments-and-settings-folder-127gb?forum=w7itproinstall)

## Perflogs

It is special system folder.<br>
It stores system log files that can be used to detect errors, system issues, performance related reports and so on.

## Program Files

This is very important folder.<br>
It stores programs that user installed such as:
- internet browsers:
   - Firefox
   - Opera
   - Google Chrome
- mail programs:
   - Mozilla Thunderbird
- game software:
   - Steam
   - Blizzard
   - RockStar
- virtual machine programs:
   - Oracle VirtualBox
   - VMWare
- developer programs:
   - Visual Studio
   - Sublime Text
   - Unity Engine
- many other programs

From Wikipedia: `[...] that are not part of the operating system are conventionally installed`.

Program Files has the Common Files folder which stores data shared between different applications.

## Program Files (x86)

It has the same purpose as Program Files but it's for installing 32 bit programs.

## Program Data

According to Microsoft: `this folder is used for application data that is not user specific`
Some programs' settings might be stored here.
This folder is shared to all users.

Source: [How to geek](https://www.howtogeek.com/278562/what-is-the-programdata-folder-in-windows/)

## Recovery

[tenforums](https://www.tenforums.com/general-support/4848-recovery-folder-c.html):

`contains WinRE.wim if you don't have a separate recovery partition. Deleting this would stop advanced startup options working. It is normally a system directory so you can't see it just by showing hidden files. `
So common files here could be:
- `boot.sdi`
- `Winre.wim`

Winre.wim is responsible for opening recovery environment which is used for special purposes.

![Windows recovery](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/windows_recovery.png)

## System Volume Information

[How to geek](https://www.howtogeek.com/282214/what-is-the-system-volume-information-folder-and-can-i-delete-it/):

It is system folder and access to it is denied.<br>
Windows stores here `restore points`.

It is special folder for each drive in Windows.

## Users

It's very important folder which consists of users' folders.<br>
Each user's folder has special folders such as:
- AppData
- Contacts
- Desktop (desktop files and recycle bin)
- Downloads (files downloaded for example in Google Chrome)
- Music
- Videos
- Pictures
- and so on

AppData is a special hidden folder which contains settings and custom information about the applications.

## Windows

It's the most important folder for all the systems' files in Windows:
- boot files - used to detect and load the system by BIOS
- all system apps (notepad, calculator, paint, command prompt, powershell, windows explorer)
- registry (`regedit.exe` - very important app, it's like hierarchical database for sonfiguration files)
- the kernel of the system (`ntoskrnl.exe` - it's the main app that make Windows works)
- task manager
- mmc (Microsoft Management Console - special program for administration and computer management)
- many other system apps...



*more coming soon...*

