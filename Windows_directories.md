# C:\
### Let's start with all the folders and files in the C: "root" directory^:
| Name | Hidden | Folder / File |
| ----- | ----- | ----- |
| $GetCurrent | Yes | Folder |
| $RecycleBin | Yes | Folder |
| $Config.Msi | Yes | Folder |
| Documents and Settings | Yes | Folder |
| Downloads | No | Folder |
| NVIDIA^ | No | Folder |
| PerfLogs | No | Folder |
| Program Files | No | Folder |
| Program FIles (x86) | No | Folder |
| Program Data | Yes | Folder |
| Recovery | Yes | Folder |
| System Volume Information | Yes | Folder |
| Users | No | Folder |
| Windows | No | Folder |
| xampp^ | No | Folder |
| hiberfil.sys | Yes | File |
| pagefile.sys | Yes | File |
| swapfile.sys | Yes | File |

> ^ note: these files / folders aren't on "clean" Windows machine, it's from my computer

> If you want to see the hidden files / filders you need to mark the `Hidden items` option in `View` tab in File Explorer

![mark hidden](https://raw.githubusercontent.com/frawojej/console_tricks/main/img/mark_hiddens.png)

## $GetCurrent

$GetCurrent is a folder which is created by Windows 10 upgrades.
It contains logs about the upgrade and the necessary and essential for the update.
After the update it leaves the data.
It should be usually deleted after update.
However, sometimes these files aren't deleted and could accumulate on disk.

Source: [https://www.computertechreviews.com/definition/getcurrent/](https://www.computertechreviews.com/definition/getcurrent/)
Good article: [https://superuser.com/questions/1322503/can-i-safely-delete-folder-getcurrent-in-windows-10](https://superuser.com/questions/1322503/can-i-safely-delete-folder-getcurrent-in-windows-10)