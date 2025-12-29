# OverTheWire Bandit: Levels 6–10

---


## Level 6 → Level 7 

**Task:**

Find a file owned by **user bandit7**, **group bandit6**, and **33 bytes in size**.

**Command Used:**
```bash
find / -user bandit7 -group bandit6 -size 33c
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
**Explanation:**

The find command was used to search the entire filesystem for files matching specific ownership and size constraints.
* `user bandit7` filters files owned by bandit7
* `group bandit6` filters files belonging to group bandit6
* `size 33c` matches files of exactly 33 bytes
  since thsese filters were showing many permission restricted files 
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
