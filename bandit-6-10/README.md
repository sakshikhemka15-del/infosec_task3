# OverTheWire Bandit: Levels 6–10

---


## Level 6 → Level 7 

**Task:**

Find a file owned by **user bandit7**, **group bandit6**, and **33 bytes in size**.

**Command Used:**
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
find / -user bandit7 -group bandit6 -size 33c
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
**Explanation:**

The find command was used to search the entire filesystem for files matching specific ownership and size constraints.
* `user bandit7` filters files owned by bandit7
* `group bandit6` filters files belonging to group bandit6
* `size 33c` matches files of exactly 33 bytes
* since thsese filters were showing many permission restricted files 
* `2>/dev/null` suppresses permission denied errors
  Redirecting `2` to `/dev/null` discards those error messages so that only valid results are shown.
  
**Output:**

```bash
/var/lib/dpkg/info/bandit7.password
morbNTDkSW6jILoCyMdo1ALFvaaj
```
**Flag:**

```bash
morbNTDkSW6jILoCyMdo1ALFvaaj
```

## Level 7 → Level 8 

**Task:**

Find the password for the next level from a file named `data.txt`. The password is stored on the line containing the word **`millionth`**.

**Command Used:**
```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
cat data.txt
grep millionth data.txt
```
**Explanation:**

The grep command was used to efficiently search the file:
* `grep` searches for a specific word inside a file
* `millionth` is the keyword given in the level description
* `data.txt` is the file being searched
  
**Output:**

```bash
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
**Flag:**

```bash
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

## Level 8 → Level 9

**Task:**

Find the password stored in data.txt.The password is the only line that appears exactly once in the file.

**Command Used:**
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
sort data.txt | uniq -u
```
**Explanation:**

To solve this:
* `sort data.txt` arranges all lines so identical lines are grouped together
* `uniq -u` prints only the lines that occur once
* `|` takes the output of the command on the left and feeds it as input to the command on the right.
  
**Output/Flag:**

```bash
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

## Level 9 → Level 10

**Task:**

Find the password in data.txt.
The file contains mostly non-readable characters, but the password is human-readable and preceded by several = characters.

**Command Used:**
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
cat data.txt
strings data.txt | grep '=='
```
**Explanation:**

The file data.txt contains binary data mixed with unreadable characters, so using cat does not clearly show the password.

To solve this:
* `strings` extracts only human-readable text from a binary file.
* `|` sends the readable output to the next command.
* `grep '=='` filters lines that contain the == symbol
  
**Output**

```bash
========== the
========== password
E========== is
5========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
**Flag:**

```bash
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
## Level 10 → Level 11

**Task:**

Find the password stored in data.txt, which contains Base64 encoded data.

**Command Used:**
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
cat data.txt
base64 -d data.txt
```
**Explanation:**

Base64 is an encoding method.
Its purpose is to convert binary data into readable ASCII characters so it can be safely stored or transmitted.

To solve this:
* `base64` is the command-line utility used to work with Base64-encoded data
*  `-d` flag tells the system to decode the scrambled string and unwrap it back to  original plain text .
  
  
**Output**

```bash
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
**Flag:**

```bash
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
