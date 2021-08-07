# C:\
### Let's start with all the folders and files in the C: "root" directory^:
| Name | Folder / File / Shortcut | Hidden | Protected operating system file |
| ----- | ----- | ----- | ----- |
| $GetCurrent | Folder | Yes | No |
| $RecycleBin | Folder | Yes | Yes |
| $Config.Msi | Folder | Yes | Yes |
| Documents and Settings | Shortcut | Yes | Yes |
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

Sources: [https://www.lifewire.com/what-is-an-sid-number-2626005](https://www.lifewire.com/what-is-an-sid-number-2626005)

YT: [https://youtu.be/jk8Io_cgYyY](https://youtu.be/jk8Io_cgYyY)

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
one starting with `$I`
second starting with `$R`
and the third called `desktop.ini`

The `$I` file contains metadata about deleted file (deletion time, path...).
The `$R` file include data inside the file.

They get random file name to avoid name conflicts.\

The `$I` file consists of:

File header, always `02 00 00 00 00 00 00 00`

Deleted file size, also 8 bytes

Deletion date, also 8 bytes

File name length (how many bytes the file has), 4 bytes

Original full path of file with original file name


*more coming soon...*

