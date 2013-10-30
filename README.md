Dayz-Linux-Server
=================

A private hive DayZ 1.8.0.3 server on Linux

Installation instructions
=========================

1. The following programs must be installed on your Linux system: screen, tar, gcc, perl, mysql.

2. Download and install newest ArmA beta patch (http://www.arma2.com/beta-patch.php).

3. Copy the whole "ArmA 2: Operation Arrowhead" directory from Windows to server Linux-directory.<br>
   ArmA2 directory should contain subdirectories "Addons", "Dta", "Expansion", etc.<br>
   Example: pack with PKZIP (WinZip, PowerArchiver, etc.) on Windows and unpack with "unzip" on Linux.<br>
   DO NOT use upper case letters in the ArmA2 directory name (or in any files that the server uses 
   like missions or mods):<br>
   GOOD: "/home/bob/arma2arrowhead"<br>
   BAD:  "/home/bob/ArmA2ArrowHead"

3. Download and install DayZ Mod 1.8.0.3 (http://se1.dayz.nu/latest/1.8.0.3/%40Client-1.8.0.3-Full.rar).

4. Run ./install<br>
   Watch the messages - they might inform you whether your installation
   failed. Double check that all directories were renamed to lower case.
   Remove any .dll files you might still find (in battleye, expansion and
   expansion/battleye directories).<br>
   When adding mission .pbo's or mods remember to run ./tolower again or
   manually change the filenames to lowercase.<br> ANY uppercase letter in
   a filename will crash the server!<br>
   $ for x in *; do mv $x `echo $x | tr [A-Z] [a-z]`; done

5. Create database and load database.sql into Mysql.<br>
   <pre>LOAD DATA INFILE 'object_init_data.txt' INTO TABLE Object_init_DATA;</pre><br>
   $ chmod +x install server *.sh *.pl<br>
   $ sudo apt-get install libjson-xs-perl 

6. Run ./server.sh for test<br>
   Watch the messages - they might inform you whether your installation failed.

7. Run ./restarter.pl<br>
   $ screen -r




