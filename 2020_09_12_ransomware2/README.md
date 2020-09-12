# Scripts for the blogpost: 2020_09_12

To use the scripts first you have to modify the variables in each file. Command line parameters/arguments can't be provided, so in this version of the scripts you have to use SED to overwrite the placeholders.

Used placeholders:
* $ARCHIVEDIR$ : The name of the Sysmon archive directory on the C drive
* $COMPUTERNAME$ : Used together with the username
* $USERNAME$ : Used together with the computername
* $HONEYFILE$ : Path to the honeyfile you want to monitor
* $PROCDUMPANDKILLSCRIPT$ : Path to the procdumpandkill script (script nr. 5)
* $PROCDUMP$ : path to the procdump binary
* $SSHKEY$ : path to the ssh key
* $BACKUPPATH$ : full remote path for scp backup in this format: user@serverip:/path/to/the/folder/


You can use SED to change each variable. The syntax of sed is the following:
sed -i 's/old-text/new-text/g' filename.txt

So here the way to replace $ARCHHIVEDIR$ to SafeHaven in each file in the folder. This way the archive folder going to be C:\SafeHaven (actually iy is going to be on each partition but I only use it on the C partition):

sed -i 's/\$ARCHIVEDIR\$/SafeHaven/g' ./*

You have to escape the command characters, be aware of this.


sed -i 's/\$COMPUTERNAME\$/WinForTest3/g' ./*

sed -i 's/\$USERNAME\$/WinForTest/g' ./*

sed -i 's/\$HONEYFILE\$/C:\\Users\\WinForTest\\Ransomware\\honeyfile.txt/g' ./*

sed -i 's/\$PROCDUMPANDKILLSCRIPT\$/C:\\Users\\WinForTest\\Documents\\scripts\\5_procdumpandkill_script.ps1/g' ./*

sed -i 's/\$PROCDUMP\$/C:\\Users\\WinForTest\\Documents\\Procdump\\procdump64.exe/g' ./*

sed -i 's/\$SSHKEY\$/C:\\Users\\WinForTest\\Documents\\testlinux_key.pem/g' ./*

sed -i 's/\$BACKUPPATH\$/winfortest@51.103.140.118:\/home\/winfortest\/SafeHaven\//g' ./*



*I haven't created one big script out of the code, because I needed them separatly for other codes, but feel free to put them together into 1 powershel cmdlet if needed.*