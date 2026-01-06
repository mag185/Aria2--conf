## Quick Setup Steps

### 1. Create configuration directory and files

**Linux/Mac:**
```bash
mkdir -p ~/.aria2
touch ~/.aria2/aria2.conf
touch ~/.aria2/aria2.session
touch ~/.aria2/dht.dat
touch ~/.aria2/dht6.dat
```

**Windows:**
```powershell
mkdir C:\Users\%USERNAME%\.aria2
type nul > C:\Users\%USERNAME%\.aria2\aria2.conf
type nul > C:\Users\%USERNAME%\.aria2\aria2.session
```

### 2. Edit paths in the config file

Replace `/home/username/` with your actual home directory path:
- Linux: `/home/yourusername/`
- Mac: `/Users/yourusername/`
- Windows: `C:/Users/yourusername/` (use forward slashes)

### 3. Set your RPC secret token

Change this line to a secure password:
```ini
rpc-secret=your_secret_token_here
```

### 4. Run Aria2 as daemon

```bash
aria2c --conf-path=/home/username/.aria2/aria2.conf -D
```

### 5. (Optional) Use a WebUI

Popular WebUIs for Aria2:
- **AriaNg**: https://github.com/mayswind/AriaNg
- **webui-aria2**: https://github.com/ziahamza/webui-aria2

---

## Keep BT Trackers Updated

For best torrent performance, regularly update your tracker list:

**Get updated trackers from:**
https://github.com/ngosang/trackerslist

**Quick update command (Linux/Mac):**
```bash
curl -s https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_best.txt | \
  grep -v '^$' | tr '\n' ',' | sed 's/,$//' > /tmp/trackers.txt
echo "bt-tracker=$(cat /tmp/trackers.txt)"
```

This configuration is optimized for:
- Fast multi-connection downloads
- Reliable resume/session management
- Good BitTorrent performance with DHT and trackers
- Remote control via RPC

Adjust the paths and settings according to your needs!
