# Linux User & Group Configuration Files

Linux manages **users** and **groups** using several important configuration files. These files store essential information such as **user accounts, passwords, groups, and security settings**. 

## Configuration Files

- **`/etc/passwd`** - Stores user account information.
- **`/etc/shadow`** - Stores encrypted passwords and security policies.
- **`/etc/group`** - Stores group information.
- **`/etc/gshadow`** - Stores secure group details.


## `/etc/passwd` – User Account Information

This file contains **basic details of all user accounts** in the system, including **username, UID, GID, home directory, and default shell**.

### File Format
Each line represents a **user account** with the following format:

```bash
username:x:UID:GID:user_info:home_directory:shell
```

### Example Entry
```bash
john:x:1001:1001:John Doe:/home/john:/bin/bash
```

### Breakdown
- **`john`** → Username  
- **`x`** → Placeholder for password (stored in `/etc/shadow`)
- **`1001`** → User ID (UID)
- **`1001`** → Group ID (GID)
- **`John Doe`** → User description
- **`/home/john`** → Home directory
- **`/bin/bash`** → Default shell


## `/etc/shadow` – Secure Password Storage

Stores **encrypted passwords** and **password aging policies** for users.

### File Format
Each line represents a **user password entry** with the following format:

```bash
username:encrypted_password:last_changed:min_age:max_age:warn:inactive:expire:reserved
```

### Example Entry
```bash
john:$6$somehash:17542:0:99999:7::::
```

### Breakdown
- **`john`** → Username  
- **`$6$somehash`** → Encrypted password  
- **`17542`** → Days since the last password change  
- **`0`** → Minimum days before changing password  
- **`99999`** → Maximum password validity days  
- **`7`** → Warning days before password expires  

## `/etc/group` – Group Information

Stores **group names, GIDs, and group members**.


### File Format
Each line represents a **group entry** in the following format:

```bash
groupname:x:GID:member1,member2,member3
```

### Example Entry
```bash
developers:x:1002:alice,bob,john
```

### Breakdown
- **`developers`** → Group name  
- **`x`** → Placeholder (group password is in `/etc/gshadow`)  
- **`1002`** → Group ID (GID)  
- **`alice, bob, john`** → Members of the group  



## `/etc/gshadow` – Secure Group Management

Stores **group passwords and administrator settings**.

### Access
- **Restricted** (Only root can read it).

### File Format
Each line represents a **secure group entry** in this format:

```bash
groupname:encrypted_password:group_admins:group_members
```

### Example Entry
```bash
developers:$6$somehash:alice,bob:alice,bob,john
```

### Breakdown
- **`developers`** → Group name  
- **`$6$somehash`** → Encrypted password  
- **`alice,bob`** → Group administrators  
- **`alice,bob,john`** → Group members  



# **Adding Users in Linux**  

Linux provides two main commands for adding users: `useradd` and `adduser`.  

- **`useradd`**: A low-level command for creating new user accounts.  
- **`adduser`**: A user-friendly wrapper for `useradd` (available in Debian-based systems).  


## **`useradd`**  
The `useradd` command is used to create a new user account in Linux.  

### **Syntax**  
```bash
useradd [options] username
```

### **Examples**  

- **Create a new user:**  
  ```bash
  useradd newuser
  ```

- **Create a user with a specific home directory:**  
  ```bash
  useradd -d /home/customhome newuser
  ```

- **Create a user with a specific shell:**  
  ```bash
  useradd -s /bin/zsh newuser
  ```

- **Create a user with a specific user ID (UID):**  
  ```bash
  useradd -u 1050 newuser
  ```

- **Create a user and assign it to a group:**  
  ```bash
  useradd -g developers newuser
  ```

- **Create a user with an expiration date (YYYY-MM-DD format):**  
  ```bash
  useradd -e 2025-12-31 newuser
  ```

- **Create a system user (for services):**  
  ```bash
  useradd -r sysuser
  ```

- **Set a password for the user:**  
  ```bash
  passwd newuser
  ```


## **`adduser`**  
The `adduser` command is a user-friendly alternative to `useradd`, available in Debian-based distributions. It provides an interactive way to add users.  

### **Syntax**  
```bash
adduser username
```

### **Examples**  

- **Create a new user interactively:**  
  ```bash
  adduser newuser
  ```
  *(This prompts for user information, including password, full name, and home directory.)*  

- **Create a user and specify the home directory:**  
  ```bash
  adduser --home /custom/home newuser
  ```

- **Create a user and specify the shell:**  
  ```bash
  adduser --shell /bin/zsh newuser
  ```

- **Create a user and assign it to a specific group:**  
  ```bash
  adduser newuser developers
  ```

- **Add an existing user to a secondary group:**  
  ```bash
  adduser newuser sudo
  ```

- **Create a system user (for services):**  
  ```bash
  adduser --system sysuser
  ```


## **Differences Between `useradd` and `adduser`**

| **Feature**               | **`useradd`**                                  | **`adduser`**                                      |
|---------------------------|------------------------------------------------|----------------------------------------------------|
| **Type**                   | Low-level command (more control)               | High-level, interactive tool (user-friendly)       |
| **Home Directory**         | Not created by default unless `-m` option used | Automatically created with sensible permissions    |
| **Password**               | Not set by default                             | Password set interactively during user creation   |
| **Additional Info**        | No prompts for user info                       | Prompts for full name, phone number, etc. (optional)|
| **Groups**                 | Needs `-G` option to assign groups             | Prompts to add the user to groups                  |
| **Shell**                  | Needs `-s` option to specify shell             | Uses `/bin/bash` by default                        |
| **Default Use Case**       | Typically used in scripts, automation, or by sysadmins | Typically used for creating users interactively    |
