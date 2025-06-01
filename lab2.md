# General Commands

## **`cat`**

The `cat` (short for concatenate) command is one of the most commonly used Linux commands. It is used to view, create, concatenate, and manipulate text files.

It can:

- Display the contents of a file.
- Merge multiple files into a single file.
- Create new files.
- Append content to an existing file.

### **Syntax:**  
```bash
cat [OPTION] [FILE...]
```
Where:  
- `[OPTION]` refers to flags that modify the behavior of `cat`.  
- `[FILE...]` specifies one or more files to read and process.  


### **Examples:**

- Create a new file and add content:
   ```bash
   cat > file.txt
   ```
   ```
   This is a test file.
   It contains random text.
   Used for testing purposes.
   ```


   (Press **Ctrl + D** to save and exit.)

- View the content of a file:
   ```bash
   cat file.txt
   ```

- Display a file with scrolling:
   ```bash
   cat file.txt | less
   ```
   or simply:
   ```bash
   less file.txt
   ```
- Append content to an existing file:
   ```bash
   cat >> file1.txt
   ```
- Combine multiple files into one:
   ```bash
   cat file.txt file1.txt > merged.txt
   ```

- Display line numbers while viewing a file:
   ```bash
   cat -n filename
   ```
- Remove extra blank lines in a text file:
    ```bash
    cat -s file.txt
    ```

Linux provides several commands to view the contents of a file without opening a text editor. The `less` and `more` commands are commonly used for this purpose.


# **`less`**

The `less` command allows you to view the contents of a file one screen at a time. 

### **Syntax**
```
less [OPTIONS] filename
```

### **Examples**

1. View a file using `less`:
   ```bash
   less file.txt
   ```
   This opens `file.txt` in the `less` viewer.

2. Scroll down one page at a time:
   - Press `Space` or `PgDn`

3. Scroll up one page at a time:
   - Press `b` or `PgUp`

4. Search for a word:
   ```bash
   /word
   ```
   - Press `n` to jump to the next match.
   - Press `N` to jump to the previous match.

5. View a file with line numbers:
   ```bash
   less -N file.txt
   ```
   This will display line numbers alongside the text.

6. Exit `less`:
   - Press `q`.

7. Display file contents and monitor updates in real-time:
   ```bash
   less +F logfile.log
   ```
   - Similar to `tail -f`, but allows scrolling back with `Ctrl + C`.

# **`more`**

The `more` command is another pager that allows viewing file contents one page at a time. Unlike `less`, it does not allow backward navigation.

### **Syntax**
```
more [OPTIONS] filename
```

### **Examples**

1. View a file using `more`:
   ```bash
   more file.txt
   ```

2. Scroll down one page at a time:
   - Press `Space`

3. Scroll line by line:
   - Press `Enter`

4. Search for a word:
   ```bash
   /word
   ```
   - Press `n` to jump to the next match.

5. View file contents with percentage display:
   ```bash
   more -d file.txt
   ```
   - Displays a percentage indicator at the bottom.

6. Exit `more`:
   - Press `q`.


# **`head`**  

The `head` command is used to display the first few lines of a file. By default, it shows the first **10 lines** unless specified otherwise. It is useful for previewing large files without opening them completely.  


## **Syntax**  
```
head [OPTIONS] file
```

## **Examples**  

- Display the first **10 lines** of a file (default):  
  ```bash
  head file.txt
  ```

- Show the first **5 lines** of a file:  
  ```bash
  head -n 5 file.txt
  ```

- Display the first **20 bytes** of a file:  
  ```bash
  head -c 20 file.txt
  ```

- Show the first **10 lines** from multiple files:  
  ```bash
  head file1.txt file2.txt
  ```

- Display the first **15 lines** of a log file with file name:  
  ```bash
  head -n 15 logfile.txt
  ```

- Display the first 7 lines of a file efficiently: 
  ```bash
  head -n 7 file.txt
  ```


# **`tail`**  

The `tail` command is used to display the last few lines of a file. By default, it shows the last **10 lines**, but this can be adjusted using options. It is commonly used for monitoring log files in real-time.  


## **Syntax**  
```
tail [OPTIONS] file
```

## **Examples**  

- Display the last **10 lines** of a file (default):  
  ```bash
  tail file.txt
  ```

- Show the last **5 lines** of a file:  
  ```bash
  tail -n 5 file.txt
  ```

- Display the last **20 bytes** of a file:  
  ```bash
  tail -c 20 file.txt
  ```

- Show the last **10 lines** from multiple files:  
  ```bash
  tail file1.txt file2.txt
  ```

- Continuously monitor a file (useful for logs):  
  ```bash
  tail -f logfile.txt
  ```

- Monitor a file and show **5 latest lines**:  
  ```bash
  tail -n 5 -f logfile.txt
  ```

- Display the last 7 lines of a file efficiently:  
  ```bash
  tail -n 7 file.txt
  ```
