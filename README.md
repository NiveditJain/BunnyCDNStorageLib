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
Gives you information about the files stored at your Root directory as json object <br>

<b>Note :</b> We recomend in cdn_path use '/' at the end for directories

### get_file
##### Description
Downloads the file from CDN to your machine

##### Parameters
| Parameter | Description |
| :-------: | :---------: |
| cdn_path | path of file you wish to get information about |
| download_path | path to save the downloaded file in local machine, (make sure all directories already exist), if no path supplied it will download the file to your present working directory |

##### Example 
some python file in project
```
import BunnyCDNStorage
cdn_connector=BunnyCDNStorage.CDNConnector('Your FTP key','your storage zone name')
# to store in working directory
cdn_connector.get_file('images/1234.png'))
```
```
import BunnyCDNStorage
cdn_connector=BunnyCDNStorage.CDNConnector('Your FTP key','your storage zone name')
# to store at some location (make sure to supply name also in path)
cdn_connector.get_file('images/1234.png','C:\\Users\\image.png))
```
File would be downloaded at the desired path <br>

### upload_file
##### Description
Uploads your file to CDN

##### Parameters
| Parameter | Description |
| :-------: | :---------: |
| cdn_path | path of directory you wish to upload to |
| file_name | name of file to appear in CDN |
| file_path | local path where file is stored (include file also), if nothing supplied will look in your present working directory with same file name on storage |

##### Example 
some python file in project
```
import BunnyCDNStorage
cdn_connector=BunnyCDNStorage.CDNConnector('Your FTP key','your storage zone name')
print(cdn_connector.upload_file('images/forest_pictures','1234.png'))
```
Your files will be uploaded, json object for response is returned <br>

### remove
##### Description
Used to get information of all files and folders stored in a directory in CDN

##### Parameters
| Parameter | Description |
| :-------: | :---------: |
| cdn_dir | path of directory/file you wish to delete (make sure that directory ends with '/') |

##### Example 
some python file in project
```
import BunnyCDNStorage
cdn_connector=BunnyCDNStorage.CDNConnector('Your FTP key','your storage zone name')
print(cdn_connector.remove('images/'))
```
It will delete the images folder, json object for response is returned <br>
```
import BunnyCDNStorage
cdn_connector=BunnyCDNStorage.CDNConnector('Your FTP key','your storage zone name')
print(cdn_connector.remove('images/forest.png'))
```
It will delete the image(forest.png) in images folder, json object for response is returned <br>