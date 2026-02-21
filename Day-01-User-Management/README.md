# Day 01 - User Management in Linux

## 🎯 Objective
To practice user creation, modification, group management and password aging in Linux.

---

## 1️. Create Users

### Create user ankush
```
sudo useradd ankush
sudo passwd ankush
```

### Switch User
```
su - ankush
whoami
```

---

## 2️. Verify User in System Files

Check in /etc/passwd
```
grep ankush /etc/passwd
```

Check group details
```
grep ankush /etc/group
```

---

## 3️. Modify User (usermod)

### Change UID
```
sudo usermod -u 3000 jivan
```

### Change Primary Group
```
sudo groupadd chennai
sudo usermod -g chennai jivan
```

### Change Comment Field
```
sudo usermod -c "Accountant Jivan Chennai" jivan
```

### Change Home Directory
```
sudo mkdir -p /impdata/jivanhome
sudo usermod -d /impdata/jivanhome jivan
```

### Change Shell
```
sudo usermod -s /sbin/nologin jivan
```

---

## 4️. Supplementary Groups

Create groups
```
sudo groupadd hockey
sudo groupadd cricket
```

Add user to multiple groups
```
sudo usermod -a -G hockey vishal
sudo usermod -a -G cricket vaishali
```

Verify
```
id vishal
```

---

## 5️. Password Aging & Shadow File

Check shadow file
```
sudo tail /etc/shadow
```

Check password aging
```
chage -l vidya
```

Set minimum password days
```
sudo chage -m 5 vidya
```

---

## 📂 Important Files Used

- /etc/passwd
- /etc/shadow
- /etc/group
- /etc/login.defs
- /etc/default/useradd

---

## ✅ Outcome

Successfully practiced:
- User creation
- User modification
- Group management
- Password aging policies
