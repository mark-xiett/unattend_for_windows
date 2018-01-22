# Unattended-Win7
Windows 7 Unattended Install with USB Media

Directions:

Insert flash drive

diskpart  
 list disk  
 [find the flash disk]  
 select disk #  
 clean  
 create partition primary size=4000  
 active  
 format fs=fat32 quick  
 assign  
exit  

xcopy /e <source> <destination>  

Place the autounattend.xml at base of USB disk.  
Mount the install.wim via 'dism /mount-wim /wimfile:install.wim /index:1 /mountdir:mount'  
Copy the unattend.xml in the c:\windows\system32\sysprep folder  
DisMount the install.wim and commit it via 'dism /unmount-wim /mountdir:mount /commit'  

Note: KMS key is in the config
