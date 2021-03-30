# C:\
### Let's start with all the folders and files in the C: "root" directory^:
| Name | Hidden | Folder / File / Shortcut | Protected operating system file |
| ----- | ----- | ----- | ----- |
| $GetCurrent | Yes | Folder | No |
| $RecycleBin | Yes | Folder | Yes |
| $Config.Msi | Yes | Folder | Yes |
| Documents and Settings | Yes | Shortcut | Yes |
| Downloads | No | Folder | No |
| NVIDIA^ | No | Folder | No |
| PerfLogs | No | Folder | No |
| Program Files | No | Folder | No |
| Program FIles (x86) | No | Folder | No |
| Program Data | Yes | Folder | No |
| Recovery | Yes | Folder | Yes |
| System Volume Information | Yes | Folder | Yes |
| Users | No | Folder | No |
| Windows | No | Folder | No |
| xampp^ | No | Folder | No |
| hiberfil.sys | Yes | File | Yes |
| pagefile.sys | Yes | File | Yes |
| swapfile.sys | Yes | File | Yes |

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