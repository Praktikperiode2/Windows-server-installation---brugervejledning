

# Guide SQL Server Connection
This guide assumes you already have an SQL server and SQL management studio installed, an SQL user, has SQL authentication enabled, and correct IP configuration.


## 💻 Windows Server Set Statisk IP Adresse in Win 10
### 1. Open Network Connections
- Press __Windows Key__ + __R__
- Type: ```ncpa.cpl``` and press __Enter__

### 2. Open Network Connections
- Right-click on your active network connection (e.g., **Ethernet**)  
- Select **Properties**

### 3. Access IP Settings
- In the list, double-click:  
  **Internet Protocol Version 4 (TCP/IPv4)**

### 4. Configure Static IP
- Select: **Use the following IP address**  
- Fill in the following fields:

  - **IP address:** e.g., `10.0.1.xxx`  
  - **Subnet mask:** e.g., `255.255.255.0` (usually auto-filled)  
  - **Default gateway:** e.g., `10.0.1.1`

- Then select: **Use the following DNS server addresses**  
  - **Preferred DNS server:** e.g., `8.8.8.8`  
  - **Alternate DNS server:** e.g., `1.1.1.1`

### 5. Save Settings
- Click **OK** to close each dialog  
- Close all remaining windows

### 6. Verify Configuration
- Open **Command Prompt**  
- Type: `ipconfig` and press **Enter**  
- Confirm that the new static IP is listed under your network adapter

> 📝 **Tip:** Ensure the static IP address you choose is not already in use on the network to avoid IP conflicts.


## 🛠️ Guide: Configure SQL Server for TCP/IP Access via SQL Server Configuration Manager

### 1. Open SQL Server Configuration Manager
- Press **Start** and search for **SQL Server Configuration Manager**  
- Open the application corresponding to your installed SQL Server version (e.g., *SQL Server 2019 Configuration Manager*)

### 2. Navigate to Network Configuration
- In the left-hand pane, expand **SQL Server Network Configuration**
- Click on **Protocols for [YourServerName]**

### 3. Enable TCP/IP
- In the right pane, right-click **TCP/IP**
- Click **Enable**

### 4. Open TCP/IP Properties
- Right-click **TCP/IP** again
- Select **Properties**

### 5. Configure IP Addresses
- Go to the **IP Addresses** tab
- Scroll through the list and do the following:
  - **IP2**: Ensure the **IP Address** field contains the correct static IP of the server
  - For each active IP (especially **IPAll**), set:
    - **TCP Port**: `1433`
    - Leave **TCP Dynamic Ports** blank (empty)

### 6. Apply and Restart
- Click **Apply**, then **OK**
- You must **restart the SQL Server service** for changes to take effect:
  - In the left pane, click **SQL Server Services**
  - Right-click your SQL Server instance
  - Click **Restart**

> 💡 **Note:** Port 1433 must also be allowed through the Windows Firewall if remote connections are needed.

### 🔥 Firewall Rule (Enable SQL Server Port 1433)
1. Open **Windows Defender Firewall with Advanced Security** 
    - Press **Windows Key** + **R**, type `wf.msc`, and press **Enter**
2. Right click **Inbound Rules** in left1 panel
3. Select **New Rule...** in right panel
4. Select **Port**, and click **Next**.
5. Check **TCP**, and "Specific local ports" - write `1433` in the field.
6. Click **Next**, and select **Allow the connection**
7. Click **Next**, and select **Private**, **Domain**, and **public**.
8. Click Next, and give the rule a descriptive Name, e.g.:

    - SQL Server TCP Port 1433

9. Click **Finish**

✅ Tip:
You may also want to create a similar Outbound Rule to ensure traffic is allowed both ways if you're dealing with strict firewall environments.

🔐 Security Note:
Opening port 1433 on Public networks is generally discouraged unless absolutely necessary. Restrict access via IP scope or use a VPN.

#### Testing connection to sql

1. Open SQL Management Studio on the Host PC.
2. In servername, fill out the IP-adress of the VM, followed by a comma, the port, and \SQLEXPRESS - Example: **10.0.1.xxx,1433\\SQLEXPRESS**
3. Select "SQL Authentication"
4. Fill out the created username, and password.

### 📌 Tip: Test forbindelsen
Fra en klient i det godkendte subnet:

***powershell***
```
Test-NetConnection -ComputerName <SQL_SERVER_IP> -Port 1433 
```

Hvis du får `TcpTestSucceeded: True`, virker forbindelsen.
