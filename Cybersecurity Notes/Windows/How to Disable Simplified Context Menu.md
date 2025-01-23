Windows 11 adds a simplified context menu (when you right click on desktop). This is annoying. Remove it and bring back the original full context menu with the following steps:

1: Open Registry Editor
	Press **WIN** + **R**, and type `regedit`, then press enter
2: Navigate to the following path within the registry editor:
```
HKEY_CURRENT_USER\Software\Classes\CLSID
```
3: Right click the CLSID folder and create a new key
	select **New** > **Key** 
	Name this key
```
{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}
```
4: Then create a subkey by right clicking on the newly created key 
	Name this key
```
InprocServer32
```
.
	Ensure the default value is empty by right clicking the **Default** value in the right pane
5: Restart Windows Explorer
	in task explorer find Windows Explorer and restart it



