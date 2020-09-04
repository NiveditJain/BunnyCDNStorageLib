# BunnyCDNStorageLib
Python Lib to connect to BunnyCDNStorage

## Requirements
Requests Lib in Python, to install use

```
pip install requests
```
## How to use
Download BunnyCDNStorage.py from this repository and place it in your project folder. <br>
Make sure that you have installed Requests <br>
Just import BunnyCDNStorage in your code to get started<br>

## Functions Available

### get_storaged_objects
##### Description
Used to get information of all files and folders stored in a directory in CDN

##### Parameters
| Parameter | Description |
| :-------: | :---------: |
| cdn_path | path of directory you wish to get information about |

##### Example 
some python file in project
```
import BunnyCDNStorage
cdn_connector=BunnyCDNStorage.CDNConnector('Your FTP key','your storage zone name')
print(cdn_connector.get_storaged_objects('/'))
```
Gives you information about the files stored at your Root directory. <br>

<b>Note :</b> We recomend in cdn_path use '/' at the end for directories