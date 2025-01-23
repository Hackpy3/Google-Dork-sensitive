# Google-Dork-sensitive
Below is a collection of commonly used Google dorks to uncover sensitive information on websites. Use these responsibly and only for ethical purposes, such as security assessments on websites you own or have permission to analyze.

---

### **1. Directory Listings**
- **Open directories:**
  ```
  intitle:"index of" "parent directory"
  ```

- **With specific file types:**
  ```
  intitle:"index of" ext:log
  ```
  *(For log files)*

  ```
  intitle:"index of" ext:sql
  ```
  *(For SQL dump files)*

  ```
  intitle:"index of" ext:backup | ext:bak | ext:old
  ```
  *(For backup files)*

---

### **2. Configuration Files**
- **Exposed `.env` files (often containing credentials):**
  ```
  ext:env "DB_PASSWORD" | "DB_USER"
  ```

- **Exposed configuration files:**
  ```
  ext:config | ext:ini | ext:yaml | ext:conf
  ```

---

### **3. Version Control Folders**
- **Exposed Git repositories:**
  ```
  intitle:"index of" ".git"
  ```

- **Exposed SVN repositories:**
  ```
  intitle:"index of" ".svn"
  ```

---

### **4. Database Files**
- **SQL Dumps:**
  ```
  ext:sql "insert into"
  ```

- **Access databases:**
  ```
  ext:mdb | ext:accdb
  ```

---

### **5. Login Portals**
- **Generic admin login pages:**
  ```
  inurl:admin | inurl:login | inurl:signin
  ```

- **Specific CMS logins (e.g., WordPress):**
  ```
  inurl:wp-admin | inurl:wp-login
  ```

---

### **6. Email Addresses**
- **Find exposed email lists:**
  ```
  filetype:xls | filetype:csv "email"
  ```

---

### **7. Password Files**
- **Text files containing passwords:**
  ```
  ext:txt "password"
  ```

- **Config files containing passwords:**
  ```
  ext:xml "password"
  ```

---

### **8. Logs and Debug Files**
- **Log files:**
  ```
  ext:log "error" | "debug"
  ```

- **Debug information:**
  ```
  inurl:debug | inurl:trace
  ```

---

### **9. Cameras and IoT Devices**
- **Search for live cameras:**
  ```
  intitle:"Live View / - AXIS" | intitle:"live view" | inurl:view/view.shtml
  ```

---

### **10. Sensitive Documents**
- **PDF files:**
  ```
  ext:pdf "confidential" | "restricted"
  ```

- **Excel files:**
  ```
  ext:xls | ext:xlsx "confidential"
  ```

---

### **11. Error Messages**
- **PHP errors revealing sensitive paths:**
  ```
  "PHP Parse error" | "PHP Warning" | "PHP Error"
  ```

- **MySQL errors:**
  ```
  "SQL syntax" | "MySQL server version"
  ```

---

### **12. Security Cameras**
- **Unsecured IP cameras:**
  ```
  inurl:"/view/view.shtml"
  ```

- **Common camera brands:**
  ```
  inurl:"/webcam.html" | inurl:"/view.shtml"
  ```

---

### **13. SSH and Private Keys**
- **Exposed private keys:**
  ```
  ext:pem | ext:ppk
  ```

---

### **14. Specific Technologies**
- **WordPress config files:**
  ```
  inurl:wp-config.php
  ```

- **Joomla configuration files:**
  ```
  inurl:configuration.php
  ```

---

### **15. Miscellaneous**
- **Exposed credentials in GitHub repos:**
  ```
  site:github.com "DB_PASSWORD" | "API_KEY"
  ```

- **Apache server status pages:**
  ```
  intitle:"Apache Status"
  ```

- **phpMyAdmin instances:**
  ```
  inurl:"phpMyAdmin/" | inurl:"pma/"
  ```

---
Here’s an expanded list of Google dorks for discovering exposed version control folders. Remember, these should only be used for ethical purposes, such as testing your own websites or performing authorized security assessments. Misuse can have serious legal and ethical consequences.

---

### **Version Control Folders**

#### **Git (.git)**
- **Standard Git directories:**
  ```
  intitle:"index of" ".git"
  ```

- **Search for `HEAD` files in Git repositories:**
  ```
  inurl:"/.git/" "HEAD"
  ```

- **Search for Git config files:**
  ```
  inurl:"/.git/config"
  ```

- **Search for Git logs:**
  ```
  inurl:"/.git/logs/"
  ```

---

#### **Subversion (.svn)**
- **Standard SVN directories:**
  ```
  intitle:"index of" ".svn"
  ```

- **Search for `entries` files in SVN repositories:**
  ```
  inurl:"/.svn/entries"
  ```

- **Search for SVN `wc.db` files:**
  ```
  inurl:"/.svn/wc.db"
  ```

---

#### **Mercurial (.hg)**
- **Standard Mercurial directories:**
  ```
  intitle:"index of" ".hg"
  ```

- **Search for `hgrc` config files:**
  ```
  inurl:"/.hg/hgrc"
  ```

- **Search for Mercurial manifests:**
  ```
  inurl:"/.hg/store"
  ```

---

#### **Bazaar (.bzr)**
- **Standard Bazaar directories:**
  ```
  intitle:"index of" ".bzr"
  ```

- **Search for Bazaar `branch.conf` files:**
  ```
  inurl:"/.bzr/branch.conf"
  ```

- **Search for Bazaar repository files:**
  ```
  inurl:"/.bzr/repository"
  ```

---

#### **CVS (Concurrent Versions System)**
- **CVS directories:**
  ```
  intitle:"index of" "CVS"
  ```

- **Search for `Root` files in CVS:**
  ```
  inurl:"/CVS/Root"
  ```

- **Search for CVS log files:**
  ```
  inurl:"/CVS/Entries"
  ```

---

#### **Perforce**
- **Perforce workspace settings:**
  ```
  intitle:"index of" "p4config.txt"
  ```

- **Search for Perforce `.p4ignore` files:**
  ```
  inurl:"/.p4ignore"
  ```

---

#### **RCS (Revision Control System)**
- **Standard RCS directories:**
  ```
  intitle:"index of" "RCS"
  ```

- **Search for RCS log files:**
  ```
  inurl:"/RCS/" ext:log
  ```

---

### **Tips to Secure Version Control Systems**
1. **Block access** to version control directories with server configuration files like `.htaccess` or Nginx rules.
2. **Use `.gitignore` or equivalent** to exclude sensitive files from version control.
3. **Deploy code securely** to production without version control directories.
4. **Monitor for accidental exposure** by using tools like Shodan or internal scanners.

Let me know if you want more specific dorks or guidance on securing your servers!

### **Tips for Ethical Usage**
1. **Always have permission** to test the websites you search.
2. **Secure your own systems** against these vulnerabilities:
   - Restrict access to sensitive files.
   - Disable directory listing.
   - Use `.htaccess` to block direct access to sensitive directories.
3. **Report vulnerabilities** to site owners or security teams responsibly.

Let me know if you'd like detailed steps on securing systems or reporting vulnerabilities.
