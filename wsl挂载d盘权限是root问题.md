mount -l查看发现
```
D:\ on /mnt/d type drvfs (rw,noatime,uid=0,gid=0,metadata,case=off)


进入 /mnt/
ls -l 
是root权限导致不能在 上面创建文件

解决

sudo touch /etc/wsl.conf
sudo nano /etc/wsl.conf
：
# Let’s enable extra metadata options by default
[automount]
enabled = true
root = /mnt/
#options = "metadata,umask=22,fmask=11"
options = "metadata,uid=1000,gid=1000" #当前用户
mountFsTab = false

#Let’s enable DNS – even though these are turned on by default, we’ll specify here just to be explicit.
[network]
generateHosts = true
generateResolvConf = true

#All windows program shoulbe be normally run in wsl. great!
[interop]
enable = true
appendWindowsPath = true


```
