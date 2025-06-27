# Setup-and-Use-a-Firewall-on-Linux


1. sudo apt install ufw(Uncomplicated Firewall)

┌──(kali㉿kali)-[~]
└─$ sudo apt install ufw
[sudo] password for kali: 
ufw is already the newest version (0.36.2-9).
The following packages were automatically installed and are no longer required:
  libbfio1  libegl-dev  libgl1-mesa-dev  libgles-dev  libgles1  libglvnd-core-dev  libglvnd-dev  libsuperlu6
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1758

2. ufw --version
     ufw --version
          ufw 0.36.2
               Copyright 2008-2023 Canonical Ltd.

3. sudo ufw enable
   sudo ufw enable     
Firewall is active and enabled on system startup

4. sudo ufw status verbose
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
23                         DENY IN     Anywhere                  
23 (v6)                    DENY IN     Anywhere (v6)             
22 (v6)                    ALLOW IN    Anywhere (v6) 

5.  sudo ufw deny 23       
Skipping adding existing rule
Skipping adding existing rule (v6)


6. sudo ufw status numbered
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] 23                         DENY IN     Anywhere                  
[ 2] 23 (v6)                    DENY IN     Anywhere (v6)             
[ 3] 22 (v6)                    ALLOW IN    Anywhere (v6) 

7. sudo apt install telnet 
telnet is already the newest version (0.17+2.6-1).
The following packages were automatically installed and are no longer required:
  libbfio1  libegl-dev  libgl1-mesa-dev  libgles-dev  libgles1  libglvnd-core-dev  libglvnd-dev  libsuperlu6
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1758

  8. telnet localhost 23    
Trying ::1...
Connection failed: Connection refused
Trying 127.0.0.1...
telnet: Unable to connect to remote host: Connection refused

9. sudo ufw allow 22       
Rule added
Skipping adding existing rule (v6)

10. sudo ufw status numbered
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] 23                         DENY IN     Anywhere                  
[ 2] 22                         ALLOW IN    Anywhere                  
[ 3] 23 (v6)                    DENY IN     Anywhere (v6)             
[ 4] 22 (v6)                    ALLOW IN    Anywhere (v6)   

11. sudo ufw delete 1       
Deleting:
 deny 23
Proceed with operation (y|n)? Y
Rule deleted

12. sudo ufw status verbose 
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
22                         ALLOW IN    Anywhere                  
23 (v6)                    DENY IN     Anywhere (v6)             
22 (v6)                    ALLOW IN    Anywhere (v6)   
