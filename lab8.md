##  Linux Lab: Process Termination and Network Configuration

### 🔹 Process Termination with `kill` and `killall`

```bash
ps aux | grep sleep
```

Lists all running processes that include the word "sleep".

```bash
sleep 500 &
```

Starts a background process that runs for 500 seconds.

```bash
kill <PID>
```

Replaces `<PID>` with the actual process ID of the `sleep` command to terminate it.

```bash
killall sleep
```

Terminates all running instances of the `sleep` command.

---

### 🔹 Network Configuration with `ifconfig` and `ip`

```bash
ifconfig
```

Displays network interfaces and their configuration (may require installation on some systems).

```bash
ip addr
```

Shows detailed IP address information for all interfaces.

---

### 🧪 Sample Output:

```
user      12345  0.0  0.0   2600   532 pts/0    S    15:15   0:00 sleep 500

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
      inet 192.168.1.10  netmask 255.255.255.0  broadcast 192.168.1.255

2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    inet 192.168.1.10/24 brd 192.168.1.255 scope global eth0
```


