Below are commonly used Bash/Linux commands related to **file and directory permissions**, with concise explanations and practical examples. These are core commands you will routinely use in system administration and DevOps work.

---

## 1. View File Permissions

### `ls -l`

Displays permissions, owner, and group.

```bash
ls -l file.txt
```

Example output:

```text
-rw-r--r-- 1 tahir tahir  1024 Jan 1 10:00 file.txt
```

Permission breakdown:

* `r` → read
* `w` → write
* `x` → execute
* First group → owner
* Second group → group
* Third group → others

---

## 2. Change Permissions – `chmod`

### Symbolic mode

```bash
chmod u+x script.sh        # add execute to owner
chmod g-w file.txt         # remove write from group
chmod o+r file.txt         # add read to others
chmod a+x script.sh        # add execute to all
```

### Numeric (octal) mode

```bash
chmod 755 script.sh        # rwx r-x r-x
chmod 644 file.txt         # rw- r-- r--
chmod 700 private.sh       # rwx --- ---
```

Permission values:

* `4` → read
* `2` → write
* `1` → execute

---

## 3. Change Ownership – `chown`

### Change owner

```bash
sudo chown tahir file.txt
```

### Change owner and group

```bash
sudo chown tahir:devops file.txt
```

### Recursive ownership change

```bash
sudo chown -R tahir:devops /var/www/html
```

---

## 4. Change Group – `chgrp`

```bash
sudo chgrp devops file.txt
```

Recursive:

```bash
sudo chgrp -R devops /opt/app
```

---

## 5. Check Detailed Permissions

### Using `stat`

```bash
stat file.txt
```

Shows:

* Access rights
* Owner
* Group
* Inode information

---

## 6. Find Files by Permission – `find`

### Find world-writable files

```bash
find / -perm -002 -type f 2>/dev/null
```

### Find executable files

```bash
find . -type f -perm /111
```

---

## 7. Default Permissions – `umask`

### View current umask

```bash
umask
```

### Set umask (temporary)

```bash
umask 022
```

Effect:

* Files → 644
* Directories → 755

---

## 8. Special Permissions

### Setuid

```bash
chmod u+s file
```

### Setgid

```bash
chmod g+s dir
```

### Sticky bit (commonly on /tmp)

```bash
chmod +t dir
```

---

## 9. Make Script Executable and Run It

```bash
chmod +x script.sh
./script.sh
```

---

If you want, I can also:

* Explain permissions **in Roman Urdu**
* Provide **real DevOps scenarios**
* Give **practice tasks** or **interview questions** on file permissions

Just let me know.
