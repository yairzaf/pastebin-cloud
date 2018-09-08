# pastebin-cloud V0.1


## python api that allows you to upload files as pastes. this requires a pastebin username,password and a developer key.


### useage:

```python
import pastebincloud #import the api

mycloudobject = pastebincloud.Cloud("myusername","myuserpassword","mydeveloperkey") #create an instance

print(mycloudobject.is_logged()) # boolean. True if loged in, False if not.

mycloudobject.print_list() #will output list of files that exist in that users pastebin

myfiles = mycloudobject.get_list() #returns the same list as string

time_delay = mycloudobject.delay() #returns how many seconds you are required to wait between pastes (premium user or not)

mycloudobject.upload("file path","upload name[optional]","private status[optional:0 default]")

#file path - the file path to upload from the local machine. (when uploading a file, the file will be converted into hex string
#                                                             and he will be divided (if necessary) into serval
#                                                             pastes according to the paste size limit.)
#upload name - [optional] the name of the paste, if not supplied the name will be the file name. 
#paste private status - 0 public, 1 unlisted, 2 private. if not supplied the default is 0.

mycloudobject.download("paste name","to path[optional]")

#paste name - the paste to download. (will download all pastes associated with 
#                                     that name in case of a file that is divided into
#                                     serval pastes)
#to path - the path to download to. if not supplied the default is the current working directory.

mycloudobject.delete("paste name")
#paste name - will delete all pastes associated with that name


```
