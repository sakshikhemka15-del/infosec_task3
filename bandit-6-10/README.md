# OverTheWire Bandit: Levels 6–10

---


## Level 6 → Level 7 (File Permissions & Ownership)

### Task
Find a file owned by **user bandit7**, **group bandit6**, and **33 bytes in size**.

### Command Used
```bash
find / -user bandit7 -group bandit6 -size 33c
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
