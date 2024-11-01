# Week 2.3 | Bash and terminal
 - terminal is nothing but another interface to do things on your machine

1. **pwd (Print Working Directory):**
   - `pwd` command displays the current working directory.
   - Example:
     ```bash
     $ pwd
     /home/username/Documents
     ```

2. **cd (Change Directory):**
   - `cd` command is used to change the current directory.
   - Example:
     ```bash
     $ cd /home/username/Documents
     ```

3. **ls (List):**
   - `ls` command lists files and directories in the current directory.
   - Example:
     ```bash
     $ ls
     file1.txt file2.txt folder1 folder2
     ```

4. **mkdir (Make Directory):**
   - `mkdir` command is used to create a new directory.
   - Example:
     ```bash
     $ mkdir new_folder
     ```

5. **touch:**
   - `touch` command creates an empty file.
   - Example:
     ```bash
     $ touch new_file.txt
     ```

6. **cat (Concatenate and Display):**
   - `cat` command displays the contents of a file.
   - Example:
     ```bash
     $ cat file.txt
     ```

7. **vi (Visual Editor):**
   - `vi` is a text editor used in the terminal. It's quite powerful but may have a learning curve for beginners.
   - Example:
     ```bash
     $ vi new_file.txt
     ```

8. **mv (Move):**
   - `mv` command is used to move files or directories from one location to another.
   - Example:
     ```bash
     $ mv file1.txt folder1/
     ```

9. **cp (Copy):**
   - `cp` command copies files or directories from one location to another.
   - Example:
     ```bash
     $ cp file1.txt folder2/
     ```

10. **clear:**
    - `clear` command clears the terminal screen.
    - Example:
      ```bash
      $ clear
      ```

11. **npm (Node Package Manager):**
    - `npm` is a package manager for JavaScript programming language (Node.js). It is used to install and manage packages/modules.
    - Example:
      ```bash
      $ npm install package-name
      ```

12. **node:**
    - `node` command runs JavaScript code outside of a web browser, typically using the Node.js runtime environment.
    - Example:
      ```bash
      $ node app.js
      ```

13. **git:**
    - `git` is a version control system used to track changes in files and collaborate with others on software development projects.
    - Example:
      ```bash
      $ git init
      ```

14. **rm (Remove):**
    - `rm` command is used to remove files or directories.
    - Example:
      ```bash
      $ rm file1.txt
      ```

15. **rmdir (Remove Directory):**
    - `rmdir` command is used to remove empty directories.
    - Example:
      ```bash
      $ rmdir empty_folder
      ```

16. **grep (Global Regular Expression Print):**
    - `grep` command searches for patterns in files.
    - Example:
      ```bash
      $ grep "search_term" file.txt
      ```

17. **find:**
    - `find` command searches for files and directories in a directory hierarchy.
    - Example:
      ```bash
      $ find /home/username -name "file.txt"
      ```

18. **chmod (Change Mode):**
    - `chmod` command changes file permissions.
    - Example:
      ```bash
      $ chmod 755 script.sh
      ```

19. **chown (Change Owner):**
    - `chown` command changes file owner and group.
    - Example:
      ```bash
      $ chown user:group file.txt
      ```

20. **curl (Client URL):**
    - `curl` command transfers data from or to a server.
    - Example:
      ```bash
      $ curl http://example.com
      ```

21. **wget:**
    - `wget` command downloads files from the web.
    - Example:
      ```bash
      $ wget http://example.com/file.zip
      ```

22. **tar (Tape Archive):**
    - `tar` command is used to create and extract archive files.
    - Example:
      ```bash
      $ tar -cvf archive.tar file1 file2
      ```

23. **zip:**
    - `zip` command compresses files into a zip archive.
    - Example:
      ```bash
      $ zip archive.zip file1 file2
      ```

24. **unzip:**
    - `unzip` command extracts files from a zip archive.
    - Example:
      ```bash
      $ unzip archive.zip
      ```

25. **df (Disk Free):**
    - `df` command displays disk space usage.
    - Example:
      ```bash
      $ df -h
      ```

26. **du (Disk Usage):**
    - `du` command estimates file and directory space usage.
    - Example:
      ```bash
      $ du -sh folder/
      ```

27. **top:**
    - `top` command displays real-time system information and processes.
    - Example:
      ```bash
      $ top
      ```

28. **ps (Process Status):**
    - `ps` command displays information about running processes.
    - Example:
      ```bash
      $ ps aux
      ```

29. **kill:**
    - `kill` command sends a signal to a process, usually to terminate it.
    - Example:
      ```bash
      $ kill 1234
      ```

30. **ping:**
    - `ping` command checks network connectivity to a host.
    - Example:
      ```bash
      $ ping google.com
      ```

31. **traceroute:**
    - `traceroute` command traces the route packets take to a network host.
    - Example:
      ```bash
      $ traceroute google.com
      ```

32. **ssh (Secure Shell):**
    - `ssh` command connects to a remote host securely.
    - Example:
      ```bash
      $ ssh user@remote_host
      ```

33. **scp (Secure Copy):**
    - `scp` command copies files between hosts securely.
    - Example:
      ```bash
      $ scp file.txt user@remote_host:/path/to/destination
      ```

34. **rsync (Remote Sync):**
    - `rsync` command synchronizes files and directories between two locations.
    - Example:
      ```bash
      $ rsync -avz source/ destination/
      ```

35. **alias:**
    - `alias` command creates shortcuts for commands.
    - Example:
      ```bash
      $ alias ll='ls -la'
      ```

36. **history:**
    - `history` command displays the command history.
    - Example:
      ```bash
      $ history
      ```

37. **man (Manual):**
    - `man` command displays the manual for a command.
    - Example:
      ```bash
      $ man ls
      ```

38. **echo:**
    - `echo` command displays a line of text.
    - Example:
      ```bash
      $ echo "Hello, World!"
      ```

39. **export:**
    - `export` command sets environment variables.
    - Example:
      ```bash
      $ export PATH=$PATH:/new/path
      ```

40. **source:**
    - `source` command executes commands from a file in the current shell.
    - Example:
      ```bash
      $ source script.sh
      ```

41. **sudo (Superuser Do):**
    - `sudo` command allows a permitted user to execute a command as the superuser or another user.
    - Example:
      ```bash
      $ sudo apt-get update
      ```

42. **apt-get:**
    - `apt-get` command is a package manager for Debian-based systems.
    - Example:
      ```bash
      $ sudo apt-get install package-name
      ```

43. **yum (Yellowdog Updater, Modified):**
    - `yum` command is a package manager for RPM-based systems.
    - Example:
      ```bash
      $ sudo yum install package-name
      ```

44. **brew:**
    - `brew` command is a package manager for macOS.
    - Example:
      ```bash
      $ brew install package-name
      ```

45. **docker:**
    - `docker` command manages Docker containers.
    - Example:
      ```bash
      $ docker run image-name
      ```

46. **kubectl:**
    - `kubectl` command manages Kubernetes clusters.
    - Example:
      ```bash
      $ kubectl get pods
      ```

47. **systemctl:**
    - `systemctl` command controls the systemd system and service manager.
    - Example:
      ```bash
      $ sudo systemctl start service-name
      ```

48. **journalctl:**
    - `journalctl` command queries and displays logs from journald.
    - Example:
      ```bash
      $ sudo journalctl -xe
      ```

49. **htop:**
    - `htop` command is an interactive process viewer.
    - Example:
      ```bash
      $ htop
      ```

50. **netstat (Network Statistics):**
    - `netstat` command displays network connections, routing tables, and interface statistics.
    - Example:
      ```bash
      $ netstat -tuln
      ```

51. **ifconfig (Interface Configuration):**
    - `ifconfig` command configures network interfaces.
    - Example:
      ```bash
      $ ifconfig
      ```

52. **ip:**
    - `ip` command shows/manipulates routing, devices, policy routing, and tunnels.
    - Example:
      ```bash
      $ ip addr show
      ```

53. **iptables:**
    - `iptables` command manages IPv4 packet filtering and NAT.
    - Example:
      ```bash
      $ sudo iptables -L
      ```

54. **ufw (Uncomplicated Firewall):**
    - `ufw` command manages firewall rules.
    - Example:
      ```bash
      $ sudo ufw enable
      ```

55. **service:**
    - `service` command runs a System V init script.
    - Example:
      ```bash
      $ sudo service apache2 start
      ```

56. **cron:**
    - `cron` is a time-based job scheduler.
    - Example:
      ```bash
      $ crontab -e
      ```

57. **crontab:**
    - `crontab` command manages cron jobs.
    - Example:
      ```bash
      $ crontab -l
      ```

58. **awk:**
    - `awk` command is a pattern scanning and processing language.
    - Example:
      ```bash
      $ awk '{print $1}' file.txt
      ```

59. **sed (Stream Editor):**
    - `sed` command is a stream editor for filtering and transforming text.
    - Example:
      ```bash
      $ sed 's/old/new/g' file.txt
      ```

60. **diff:**
    - `diff` command compares files line by line.
    - Example:
      ```bash
      $ diff file1.txt file2.txt
      ```

61. **patch:**
    - `patch` command applies a diff file to an original.
    - Example:
      ```bash
      $ patch < patchfile
      ```

62. **xargs:**
    - `xargs` command builds and executes command lines from standard input.
    - Example:
      ```bash
      $ cat file.txt | xargs -n 1 echo
      ```

63. **tee:**
    - `tee` command reads from standard input and writes to standard output and files.
    - Example:
      ```bash
      $ echo "Hello" | tee file.txt
      ```

64. **less:**
    - `less` command views file contents one screen at a time.
    - Example:
      ```bash
      $ less file.txt
      ```

65. **more:**
    - `more` command views file contents one screen at a time.
    - Example:
      ```bash
      $ more file.txt
      ```

66. **head:**
    - `head` command outputs the first part of files.
    - Example:
      ```bash
      $ head -n 10 file.txt
      ```

67. **tail:**
    - `tail` command outputs the last part of files.
    - Example:
      ```bash
      $ tail -n 10 file.txt
      ```

68. **sort:**
    - `sort` command sorts lines of text files.
    - Example:
      ```bash
      $ sort file.txt
      ```

69. **uniq:**
    - `uniq` command reports or omits repeated lines.
    - Example:
      ```bash
      $ uniq file.txt
      ```

70. **wc (Word Count):**
    - `wc` command prints newline, word, and byte counts for each file.
    - Example:
      ```bash
      $ wc file.txt
      ```

71. **basename:**
    - `basename` command strips directory and suffix from filenames.
    - Example:
      ```bash
      $ basename /home/username/file.txt
      ```

72. **dirname:**
    - `dirname` command strips the last component from file name.
    - Example:
      ```bash
      $ dirname /home/username/file.txt
      ```

73. **cut:**
    - `cut` command removes sections from each line of files.
    - Example:
      ```bash
      $ cut -d',' -f1 file.txt
      ```

74. **paste:**
    - `paste` command merges lines of files.
    - Example:
      ```bash
      $ paste file1.txt file2.txt
      ```

75. **tr (Translate):**
    - `tr` command translates or deletes characters.
    - Example:
      ```bash
      $ echo "hello" | tr 'a-z' 'A-Z'
      ```

76. **split:**
    - `split` command splits a file into pieces.
    - Example:
      ```bash
      $ split -l 10 file.txt
      ```

77. **join:**
    - `join` command joins lines of two files on a common field.
    - Example:
      ```bash
      $ join file1.txt file2.txt
      ```

78. **comm:**
    - `comm` command compares two sorted files line by line.
    - Example:
      ```bash
      $ comm file1.txt file2.txt
      ```

79. **nl (Number Lines):**
    - `nl` command numbers lines of files.
    - Example:
      ```bash
      $ nl file.txt
      ```

80. **seq:**
    - `seq` command prints a sequence of numbers.
    - Example:
      ```bash
      $ seq 1 10
      ```

81. **yes:**
    - `yes` command outputs a string repeatedly until killed.
    - Example:
      ```bash
      $ yes "Hello"
      ```

82. **bc (Basic Calculator):**
    - `bc` command is an arbitrary precision calculator language.
    - Example:
      ```bash
      $ echo "5+3" | bc
      ```

83. **expr:**
    - `expr` command evaluates expressions.
    - Example:
      ```bash
      $ expr 5 + 3
      ```

84. **factor:**
    - `factor` command prints prime factors of numbers.
    - Example:
      ```bash
      $ factor 15
      ```

85. **units:**
    - `units` command converts between different units.
    - Example:
      ```bash
      $ units "10 meters" "feet"
      ```

86. **date:**
    - `date` command displays or sets the system date and time.
    - Example:
      ```bash
      $ date
      ```

87. **cal (Calendar):**
    - `cal` command displays a calendar.
    - Example:
      ```bash
      $ cal
      ```

88. **uptime:**
    - `uptime` command tells how long the system has been running.
    - Example:
      ```bash
      $ uptime
      ```

89. **who:**
    - `who` command shows who is logged on.
    - Example:
      ```bash
      $ who
      ```

90. **w:**
    - `w` command shows who is logged on and what they are doing.
    - Example:
      ```bash
      $ w
      ```

91. **last:**
    - `last` command shows the last logins of users.
    - Example:
      ```bash
      $ last
      ```

92. **users:**
    - `users` command shows the users currently logged in.
    - Example:
      ```bash
      $ users
      ```

93. **groups:**
    - `groups` command shows the groups a user is in.
    - Example:
      ```bash
      $ groups username
      ```

94. **id:**
    - `id` command shows user and group information.
    - Example:
      ```bash
      $ id username
      ```

95. **passwd:**
    - `passwd` command changes a user's password.
    - Example:
      ```bash
      $ passwd
      ```

96. **chage (Change Age):**
    - `chage` command changes user password expiry information.
    - Example:
      ```bash
      $ sudo chage -l username
      ```

97. **chsh (Change Shell):**
    - `chsh` command changes a user's login shell.
    - Example:
      ```bash
      $ chsh -s /bin/bash
      ```

98. **chfn (Change Full Name):**
    - `chfn` command changes a user's full name.
    - Example:
      ```bash
      $ chfn username
      ```

99. **newgrp:**
    - `newgrp` command logs in to a new group.
    - Example:
      ```bash
      $ newgrp groupname
      ```

100. **su (Substitute User):**
    - `su` command changes the current user ID to that of another user.
    - Example:
      ```bash
      $ su - username
      ```

101. **login:**
    - `login` command logs into the system.
    - Example:
      ```bash
      $ login
      ```

102. **logout:**
    - `logout` command logs out of the current session.
    - Example:
      ```bash
      $ logout
      ```

103. **shutdown:**
    - `shutdown` command brings the system down.
    - Example:
      ```bash
      $ sudo shutdown -h now
      ```

104. **reboot:**
    - `reboot` command reboots the system.
    - Example:
      ```bash
      $ sudo reboot
      ```

105. **halt:**
    - `halt` command stops the system.
    - Example:
      ```bash
      $ sudo halt
      ```

106. **poweroff:**
    - `poweroff` command powers off the system.
    - Example:
      ```bash
      $ sudo poweroff
      ```

107. **init:**
    - `init` command changes the runlevel.
    - Example:
      ```bash
      $ sudo init 0
      ```

108. **runlevel:**
    - `runlevel` command prints the previous and current runlevel.
    - Example:
      ```bash
      $ runlevel
      ```

109. **telinit:**
    - `telinit` command sends signals to the init process.
    - Example:
      ```bash
      $ sudo telinit 1
      ```

110. **dmesg (Display Message):**
    - `dmesg` command prints the kernel ring buffer.
    - Example:
      ```bash
      $ dmesg
      ```

111. **lsblk (List Block Devices):**
    - `lsblk` command lists information about block devices.
    - Example:
      ```bash
      $ lsblk
      ```

112. **blkid (Block ID):**
    - `blkid` command locates/prints block device attributes.
    - Example:
      ```bash
      $ blkid
      ```

113. **mount:**
    - `mount` command mounts a filesystem.
    - Example:
      ```bash
      $ sudo mount /dev/sda1 /mnt
      ```

114. **umount:**
    - `umount` command unmounts a filesystem.
    - Example:
      ```bash
      $ sudo umount /mnt
      ```

115. **swapon:**
    - `swapon` command enables devices and files for paging and swapping.
    - Example:
      ```bash
      $ sudo swapon /swapfile
      ```

116. **swapoff:**
    - `swapoff` command disables devices and files for paging and swapping.
    - Example:
      ```bash
      $ sudo swapoff /swapfile
      ```

117. **mkfs (Make Filesystem):**
    - `mkfs` command builds a Linux filesystem.
    - Example:
      ```bash
      $ sudo mkfs.ext4 /dev/sda1
      ```

118. **fsck (Filesystem Check):**
    - `fsck` command checks and repairs a Linux filesystem.
    - Example:
      ```bash
      $ sudo fsck /dev/sda1
      ```

119. **tune2fs:**
    - `tune2fs` command adjusts tunable filesystem parameters on ext2/ext3/ext4 filesystems.
    - Example:
      ```bash
      $ sudo tune2fs -l /dev/sda1
      ```

120. **resize2fs:**
    - `resize2fs` command resizes ext2/ext3/ext4 filesystems.
    - Example:
      ```bash
      $ sudo resize2fs /dev/sda1
      ```

121. **e2fsck (Extended Filesystem Check):**
    - `e2fsck` command checks a Linux ext2/ext3/ext4 filesystem.
    - Example:
      ```bash
      $ sudo e2fsck /dev/sda1
      ```

122. **mkswap:**
    - `mkswap` command sets up a Linux swap area.
    - Example:
      ```bash
      $ sudo mkswap /swapfile
      ```

123. **badblocks:**
    - `badblocks` command searches for bad blocks in a device.
    - Example:
      ```bash
      $ sudo badblocks -v /dev/sda1
      ```

124. **mkisofs:**
    - `mkisofs` command creates an ISO 9660 filesystem.
    - Example:
      ```bash
      $ mkisofs -o image.iso /path/to/folder
      ```

125. **dd (Data Duplicator):**
    - `dd` command converts and copies files.
    - Example:
      ```bash
      $ dd if=/dev/sda of=/dev/sdb bs=4M
      ```

126. **parted:**
    - `parted` command manipulates disk partitions.
    - Example:
      ```bash
      $ sudo parted /dev/sda
      ```

127. **fdisk:**
    - `fdisk` command manipulates disk partition table.
    - Example:
      ```bash
      $ sudo fdisk /dev/sda
      ```

128. **cfdisk:**
    - `cfdisk` command is a curses-based partition table manipulator.
    - Example:
      ```bash
      $ sudo cfdisk /dev/sda
      ```

129. **sfdisk:**
    - `sfdisk` command is a scriptable partition table manipulator.
    - Example:
      ```bash
      $ sudo sfdisk -l /dev/sda
      ```

130. **mklabel:**
    - `mklabel` command creates a new disk label.
    - Example:
      ```bash
      $ sudo parted /dev/sda mklabel gpt
      ```

131. **mkpart:**
    - `mkpart` command creates a new partition.
    - Example:
      ```bash
      $ sudo parted /dev/sda mkpart primary ext4 0% 100%
      ```

