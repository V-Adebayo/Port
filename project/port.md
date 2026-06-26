# Common Ports Investigation with `netstat`

## Objective

The goal of this exercise was to identify listening ports on my Windows machine and determine which processes were using them.

---

## Commands Used

Display all active connections, listening ports, and Process IDs (PIDs):

```cmd
netstat -ano
```

Find the process associated with a PID:

```cmd
tasklist /FI "PID eq <PID>"
```

Display the Windows service running inside a `svchost.exe` process:

```cmd
tasklist /svc /FI "PID eq <PID>"
```

---

## Investigation

I started by running:

```cmd
netstat -ano
```

This displayed all active TCP and UDP connections, listening ports, connection states, and the Process ID (PID) associated with each connection.

From the output, I observed several listening ports:

| Port | State | PID |
|------|---------|------:|
| 135 | LISTENING | 1584 |
| 445 | LISTENING | 4 |
| 5040 | LISTENING | 10064 |
| 5357 | LISTENING | 4 |

I also noticed connections in different states, including:

- `LISTENING`
- `ESTABLISHED`
- `TIME_WAIT`

---

## Identifying a Process

At first, I tried checking PID **1256**.

```cmd
tasklist /FI "PID eq 1256"
```

Output:

```text
INFO: No tasks are running which match the specified criteria.
```

I realized that PID **1256** was not present in my `netstat` output, so I selected another PID.

I then ran:

```cmd
tasklist /FI "PID eq 7056"
```

Output:

```text
Image Name     PID
svchost.exe    7056
```

This showed that the process with PID **7056** was **svchost.exe**.

---

## Understanding the Connection States

### LISTENING

A service is waiting for incoming network connections.

### ESTABLISHED

A connection is active, meaning data is currently being exchanged between my computer and another device.

### TIME_WAIT

The connection has already been closed but Windows keeps it open briefly to ensure all remaining packets are handled correctly.

---

## What I Observed

- Port **135** was listening for incoming connections.
- Port **445** was also in the listening state.
- Several connections were in the **ESTABLISHED** state, indicating active communication.
- Multiple entries were in the **TIME_WAIT** state, showing recently closed connections.
- Each listening port had a Process ID (PID) that could be used to identify the owning process.

---

## What I Learned

- `netstat -ano` is useful for viewing active network connections and listening ports.
- The `-o` option displays the PID associated with each connection.
- `tasklist` can be used to identify the application or service using a specific PID.
- If a PID is not found, it may no longer exist or may have been entered incorrectly.
- Investigating ports and their associated processes is a useful skill for troubleshooting and security monitoring.

---

## Screenshots

### `netstat -ano`

![Netstat Output](screenshots/netstat-output.png)

### `tasklist`

![Tasklist Output](screenshots/tasklist-pid.png)

