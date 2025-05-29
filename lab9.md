## 🧪 Linux Lab: Connectivity Testing and File Transfer

### 🔹 Connectivity Testing with `ping`, `traceroute`, `netstat`

```bash
ping google.com
```

Sends ICMP echo requests to test if the system can reach Google's server.

```bash
traceroute google.com
```

Displays the path packets take to reach Google's server.

> On some systems, `traceroute` may need to be installed:

```bash
sudo apt install traceroute   # Debian/Ubuntu  
sudo yum install traceroute   # RHEL/CentOS
```

```bash
netstat -tuln
```

Displays active TCP/UDP listening ports and their associated IP addresses.

> Note: On newer systems, you may use `ss -tuln` as an alternative to `netstat`.

---

### 🔹 File Transfer with `scp` and `rsync`

```bash
scp /path/to/file username@remote_host:/path/to/destination
```

Securely copies a file from your system to a remote server.

```bash
scp username@remote_host:/path/to/remote_file /local/destination
```

Copies a file from a remote server to your local machine.

```bash
rsync -av /path/to/source/ username@remote_host:/path/to/destination/
```

Synchronizes files and directories to a remote server efficiently.

```bash
rsync -av username@remote_host:/path/to/source/ /local/destination/
```

Synchronizes from remote to local.

