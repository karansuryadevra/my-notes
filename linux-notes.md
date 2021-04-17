# My notes from : UNIX and Linux System Administration Handbook, 5th Edition

> The Filesystem

- Use 'umount -f' to force an unmount
- Use 'fuser -cv <mount_point>' to find the pid that is currently using the directory
- An alternative to using 'fuser' would be to use 'lsof -F'
- Important directories :  
   /boot --> contains the kernel  
   /etc  --> contains critical system and config files  
   /bin and /sbin --> contain important utilities  
   /tmp  --> temporary files  
   /dev  --> contains details of devices  
   /lib  --> shared libarry files. Generally linked with /usr/lib
   /usr  --> standard but not system-critical programs along with manuals and most libraries
   /var  --> contains spool, log and other information that grows/changes rapidly i.e. info that is variable
- /var and /usr both need to be available for the machine to boot up into multi-user mode

![alt-text](https://github.com/karansuryadevra/my-notes/blob/main/Linux%20FS%20overview.PNG)
   
- Find a standar explanation of the FS and its directories [here | http://wiki.linuxfoundation.org/en/FHS]
- Remember the permission bits as 400,200,100 ; 40,20,10 ; 4,2,1 ; The order is read,write,execute and they apply to UGO (user, group, owner)
- If the sticky bit is set on a directory, it Linux wont let you delete or rename it unless you are the owner or superuser. It is represented with a "t" in the execute bit of the others
   Eg : drwxrwxrwt  54 root root  24576 Apr 16 23:02 tmp  :
- umask is what determines the default permissions you give to a file/directory while creating it
