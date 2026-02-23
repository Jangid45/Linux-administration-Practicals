# 1️. Create Groups

```bash
groupadd pune
groupadd delhi
groupadd noida
```

Verify:

```bash
grep pune /etc/group
grep delhi /etc/group
```

---

# 2️. Create Users

```bash
useradd samiksha
useradd atharva
useradd pavan
useradd deepika
useradd abhishek
useradd shubham
```

---

# 3️. Add Users to Groups

```bash
usermod -aG delhi samiksha
usermod -aG delhi atharva

usermod -aG noida abhishek
usermod -aG noida shubham
```

Verify:

```bash
id samiksha
id abhishek
```

---

# 4️. Create Project Directory

```bash
mkdir /projectPune
chown samiksha /projectPune
chgrp delhi /projectPune
chmod 770 /projectPune
```

Check permissions:

```bash
ls -ld /projectPune
```

---

# 5️. Install ACL Package (if not installed)

```bash
dnf install acl -y
```

---

# 6️. Apply ACL Permissions

### Give full permission to pavan

```bash
setfacl -m u:pavan:rwx /projectPune
```

### Give read & execute to deepika

```bash
setfacl -m u:deepika:rx /projectPune
```

### Give full permission to noida group

```bash
setfacl -m g:noida:rwx /projectPune
```

---

# 7️. Verify ACL

```bash
getfacl /projectPune
```

---

# 8️. Remove Specific ACL Entry

```bash
setfacl -x u:deepika /projectPune
getfacl /projectPune
```

---

# 9️. Remove All ACL Entries

```bash
setfacl -b /projectPune
getfacl /projectPune
```

---

#  What We Learned

✔ Difference between normal permissions and ACL  
✔ Assign permission to specific users  
✔ Assign permission to specific groups  
✔ Remove individual ACL entries  
✔ Remove all ACL settings  

---

#  Why ACL is Important?

- When default owner/group permissions are not enough  
- When specific user needs special access  
- Used heavily in enterprise environments  

---

# Conclusion

Successfully implemented and managed Access Control Lists (ACL) for fine-grained permission control in Linux.
