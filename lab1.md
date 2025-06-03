
<h1 align="center">Basic Linux Commands</h1>

## `pwd`  
The `pwd` (Print Working Directory) command is used to display the absolute path of the current working directory. 

  ```
  pwd
  ```

## `ls`  
`ls` command Used to list the contents of a directory. It provides information about files and directories, such as names, permissions, sizes, and timestamps.

**Syntax:**  
```
ls [options] [directory]
```
**Examples:**  
- Current location available file/directory list  
  ```
  ls
  ```
- Detailed view  
  ```
  ls -l
  ```
- Show hidden files  
  ```
  ls -a
  ```
- Human-readable sizes  
  ```
  ls -lh
  ```
- Recursive listing  
  ```
  ls -R
  ```
- Sort by modification time  
  ```
  ls -lt
  ```
- List only directories  
  ```
  ls -d */
  ```

## `cd`  
Changes the current directory.  
**Syntax:**  
```
cd [directory]
```
**Examples:**  
- Go to a specific folder  
  ```
  cd /home/
  ```
- Move up one level  
  ```
  cd ..
  ```
- Go to root  
  ```
  cd /
  ```
- Return to the previous directory  
  ```
  cd -
  ```
- Go to the home directory  
  ```
  cd ~
  ```

## **System Information**  

## `date`  
- Displays the current date and time.  

  ```
  date
  ```

## `time`  
-  Displays the system's current time.  
    ```
    time
    ```

## `cal`  
- Displays a calendar for the current month.  

  ```
  cal
  ```

## `uptime`  
- Shows how long the system has been running.  
  ```
  uptime
  ```

## `uname -a`  
- Displays system and kernel information.  
  ```
  uname -a
  ```

## `lscpu`  
- Displays CPU architecture details.  
  ```
  lscpu
  ```

## `lsusb`  
- Lists USB devices connected to the system.  
  ```
  lsusb
  ```

## `df -h`  
- Shows disk space usage in a human-readable format.
  ```
  df -h
  ```

## **User and Session Information**  

## `whoami`  
- Displays the currently logged-in user.  
  ```
  whoami
  ```

## `who`
- List all logged-in users
  ```
  who
  ```

## `id`  
- Displays user ID and group information.  
  ```
  id user
  ```


## **Process and Memory Information**  

## `ps -aux`  
- Lists all running processes.  
  ```
  ps -aux
  ```

## `top`  
- Shows real-time system statistics.  
  ```
  top
  ```

## `free -h`  
- Displays memory and swap usage in a human-readable format.  

  ```
  free -h
  ```

## **Help and Documentation**  

## `man`  
Displays the manual for a command.  
**Syntax:**  
```
man [command]
```
**Example:**  
```
man ls
```

## `info`  
Provides more detailed information about a command.  
**Syntax:**  
```
info [command]
```
**Example:**  
```
info ls
```

## `help`  
Displays brief help information for built-in commands.  
**Syntax:**  
```
help [command]
```
**Example:**  
```
help cd
```

## **System Shutdown and Reboot**  

## `shutdown`  
Shuts down or reboots the system.  
**Syntax:**  
```
shutdown [options] [time]
```
**Examples:**  
- Power off immediately  
  ```
  shutdown -P now
  ```
- Restart immediately  
  ```
  shutdown -r now
  ```
- Cancel scheduled shutdown  
  ```
  shutdown -c
  ```

## `reboot`  
- Reboots the system.  
  ```
  sudo reboot
  ```

## `touch`  
Creates a new empty file or updates the timestamp of an existing file without modifying its contents.  

**Syntax:**  
```
touch [filename]
```

**Examples:**  
- Create a new empty file  
  ```
  touch myfile.txt
  ```
- Create multiple files at once  
  ```
  touch file1.txt file2.txt file3.txt
  ```
- Update the timestamp of an existing file  
  ```
  touch existingfile.txt
  ```
- Set a specific timestamp (e.g., January 1, 2024, at 12:00 PM)  
  ```
  touch -t 202401011200 myfile.txt
  ```



## `mkdir`  
Creates one or multiple directories at the specified location.  

**Syntax:**  
```
mkdir [directory_name]
```

**Examples:**  
- Create a single directory  
  ```
  mkdir new_folder
  ```
- Create multiple directories at once  
  ```
  mkdir folder1 folder2 folder3
  ```
- Create nested directories in one command  
  ```
  mkdir -p parent/child/grandchild
  ```
- Set permissions while creating a directory  
  ```
  mkdir -m 755 my_secure_folder
  ```



## `rmdir`  
Deletes an empty directory; does not work if the directory contains files.  

**Syntax:**  
```
rmdir [directory_name]
```

**Examples:**  
- Remove an empty directory  
  ```
  rmdir old_folder
  ```
- Remove multiple empty directories at once  
  ```
  rmdir dir1 dir2 dir3
  ```
- Remove nested empty directories  
  ```
  rmdir -p parent/child/grandchild
  ```


## `rm`  
Removes files or directories permanently. Be careful, as deleted files cannot be easily recovered.  

**Syntax:**  
```
rm [options] [file/directory]
```

**Examples:**  
- Remove a single file  
  ```
  rm file.txt
  ```
- Remove multiple files at once  
  ```
  rm file1.txt file2.txt file3.txt
  ```
- Remove a directory and all its contents (use with caution)  
  ```
  rm -rf foldername
  ```
- Remove files with a confirmation prompt  
  ```
  rm -i file.txt
  ```
- Remove all `.txt` files in the current directory  
  ```
  rm *.txt
  ```
- Remove all files except one specific file  
  ```
  rm !(important.txt)
  ```

