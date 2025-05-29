# Editor Tools for Linux

# **`nano` Text Editor**  

The `nano` command is a simple and user-friendly text editor for editing files directly in the terminal. It is easy to use and comes pre-installed on many Linux distributions.  


## **`nano`**  

### **Syntax**  
```
nano [OPTIONS] filename
```

### **Examples**  

- Opens `file.txt` or creates a new file if it doesn’t exist.
  ```
  nano file.txt
  ```


- `-l` shows line numbers in the editor.
  ```
  nano -l file.txt
  ```
  

- `-v` prevents accidental modifications.
  ```
  nano -v file.txt
  ```

- Open a file and position the cursor at a specific line and column:  
  ```
  nano +10,5 file.txt
  ```

- Open a file without wrapping long lines:  
  ```
  nano -w file.txt
  ```

## **Basic `nano` Keyboard Shortcuts**  

- **Save (Write to file):** `CTRL + O` (Press **Enter** to confirm)  
- **Exit nano:** `CTRL + X`  
- **Cut a line:** `CTRL + K`  
- **Paste a line:** `CTRL + U`  
- **Copy a line:** `CTRL + K` (cut) and `CTRL + U` (paste multiple times)  
- **Find text in file:** `CTRL + W` (Type text and press **Enter**)  
- **Find and replace text:** `CTRL + \` (Enter search text, then replacement text)  
- **Move to the beginning of the file:** `CTRL + Y`  
- **Move to the end of the file:** `CTRL + V`  
- **Undo last action:** `ALT + U`  
- **Redo last undone action:** `ALT + E`  

---

For more details, check the manual pages:  
```
nano --help
man nano
```


# **`vim` Text Editor**  

The `vim` (Vi IMproved) editor is a powerful, highly configurable text editor used for programming and general text editing. It is an enhanced version of `vi`, offering more features like syntax highlighting, undo levels, and plugins.  



## **`vim`**  

### **Syntax**  
```
vim [OPTIONS] filename
```

### **Examples**  

- Open a file for editing:  
  ```
  vim file.txt
  ```

- Open a file in **read-only mode**:  
  ```
  vim -R file.txt
  ```

- Open a file and jump to a specific line:  
  ```
  vim +10 file.txt
  ```

- Open multiple files:  
  ```
  vim file1.txt file2.txt
  ```
  (Use :n to go to the next file and :N to go to the previous file.) 

- Open a file in **diff mode** (compare two files):  
  ```
  vim -d file1.txt file2.txt
  ```


## **`Vim` Modes**  

Vim operates in **different modes**, each designed for specific tasks.  

### **1. Normal Mode (Esc Mode)**  
- This is the **default mode** when Vim starts.  
- Used for navigation, editing, and executing commands.  
- To enter **Normal Mode**, press:  
  ```
  Esc
  ```
- Example commands in Normal Mode:  
  - Move to the beginning of a line: `0`  
  - Move to the end of a line: `$`  
  - Move to line 50: `50G`  
  - Delete a line: `dd`  
  - Copy (yank) a line: `yy`  
  - Paste copied text: `p`  
  - Save file: `:w`  
  - Quit Vim: `:q`  
  - Force quit without saving: `:q!`  

---

### **2. Insert Mode**  
- Used for **writing and editing** text.  
- To enter **Insert Mode**, press one of the following keys in Normal Mode:  
  - `i` → Insert at cursor position  
  - `I` → Insert at the beginning of the line  
  - `a` → Append after cursor  
  - `A` → Append at the end of the line  
  - `o` → Open a new line below  
  - `O` → Open a new line above  
- To exit **Insert Mode**, press:  
  ```
  Esc
  ```  

---

### **3. Replace Mode**  
- Used to **overwrite existing text**.  
- To enter **Replace Mode**, press:  
  ```
  R
  ```
- Example:  
  - Press `R`, then type new text → **replaces** characters instead of inserting.  
  - Press `Esc` to return to Normal Mode.  

---

### **4. Visual Mode**  
- Used for **selecting text** to copy, delete, or edit.  
- To enter **Visual Mode**, press:  
  - `v` → Start **character-wise** selection  
  - `V` → Start **line-wise** selection  
  - `Ctrl + v` → Start **block selection (column mode)**  
- Example:  
  - Select multiple lines and copy:  
    ```
    V (select lines) → y
    ```
  - Select and delete text:  
    ```
    v (select text) → d
    ```
  - Select and replace text:  
    ```
    v (select text) → c (change text)
    ```
- To exit **Visual Mode**, press:  
  ```
  Esc
  ```  


## **Basic `Vim` Commands**  

- **Save file**: `:w`  
- **Quit Vim**: `:q`  
- **Save and quit**: `:wq` or `ZZ`  
- **Quit without saving**: `:q!`  
- **Find and replace**: `:%s/old/new/g`  
- **Undo last change**: `u`  
- **Redo last change**: `Ctrl + r`  
