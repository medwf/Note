To configure **UFW (Uncomplicated Firewall)** on your server to:

- **Allow all outgoing traffic**
    
- **Block all incoming traffic**
    
- **Only allow specific incoming ports** (SSH, HTTP, HTTPS)
    

You can do the following:

---

### ✅ Step-by-step UFW Configuration

1. **Reset UFW to default (optional but recommended):**
    
    ```bash
    sudo ufw reset
    ```
    
2. **Set default policies:**
    
    ```bash
    sudo ufw default deny incoming
    sudo ufw default allow outgoing
    ```
    
3. **Allow only specific incoming ports (optional):**
    
    - Allow **SSH** (port 22):
        
        ```bash
        sudo ufw allow ssh
        ```
        
    - Allow **HTTP** (port 80):
        
        ```bash
        sudo ufw allow http
        ```
        
    - Allow **HTTPS** (port 443):
        
        ```bash
        sudo ufw allow https
        ```
        
4. **Enable UFW:**
    
    ```bash
    sudo ufw enable
    ```
    

---

### 🔍 Check UFW Status

```bash
sudo ufw status verbose
```

You should see something like:

```plaintext
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
80/tcp                     ALLOW       Anywhere
443/tcp                    ALLOW       Anywhere
```

---

### 🧠 Important Notes:

- Don't skip `ufw allow ssh` if you're connected via SSH, or you’ll **lock yourself out**.
    
- By default, UFW allows **all outgoing** connections — so no need to explicitly allow them unless you've changed the default.
    
- You can also restrict access by IP, e.g.:
    
    ```bash
    sudo ufw allow from 192.168.1.100 to any port 22
    ```
    

---

Let me know if you want to **restrict SSH by IP** or **rate-limit** to prevent brute force attacks.