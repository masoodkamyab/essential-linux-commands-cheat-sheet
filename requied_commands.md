### ⚙️ **GNOME Desktop Configuration**
```shell
gsettings list-schemas  
: List all available GSettings schemas.

gsettings list-keys org.gnome.desktop.input-sources  
: Show all configurable keys for input sources.

gsettings get org.gnome.desktop.input-sources xkb-options  
: Display current keyboard options.

gsettings set org.gnome.desktop.input-sources xkb-options "['caps:none']"  
: Disable Caps Lock by remapping it to ‘No Symbol’.

gsettings reset org.gnome.desktop.input-sources xkb-options  
: Restore default keyboard options.

gsettings monitor org.gnome.desktop.input-sources xkb-options  
: Watch for changes to the xkb-options key in real time.
```


## 🔧 Parameterized Power‑User Commands

### 🔍 Find & Act

> **`find /var/log -type f -name "*.log" -mtime +7 -exec gzip --best {} \;`**  
> **Purpose:** Compress all `.log` files older than 7 days in `/var/log`.  
> **Details:**  
> - `-type f`: limit to files  
> - `-name "*.log"`: match files ending in `.log`  
> - `-mtime +7`: modified more than 7 days ago  
> - `-exec … {} \;`: run `gzip --best` on each result  

> **`find "$HOME" -type f -size +100M -print0 \| xargs -0 ls -lh`**  
> **Purpose:** List every file in your home directory larger than 100 MB.  
> **Details:**  
> - `-size +100M`: files over 100 MiB  
> - `-print0` / `xargs -0`: safely handle spaces/newlines  
> - `ls -lh`: show human‑readable sizes and permissions  

> **`find / -xdev -type f -perm /4000 -print`**  
> **Purpose:** Discover all SUID executables on the root filesystem.  
> **Details:**  
> - `-xdev`: don’t cross filesystem boundaries  
> - `-perm /4000`: match files with the SUID bit set  

---

### 🔄 Backup & Sync

> **`rsync -aHv --delete --exclude='*.cache/' /home/ortimo/ /backup/$(date +%F)/`**  
> **Purpose:** Mirror your home directory to a dated backup, pruning deletions.  
> **Details:**  
> - `-a`: archive mode (preserve perms, timestamps, symlinks)  
> - `-H`: preserve hard links  
> - `-v`: verbose output  
> - `--delete`: remove dest files missing in source  
> - `--exclude='*.cache/'`: skip cache dirs  
> - `$(date +%F)`: inserts `YYYY‑MM‑DD` folder  

> **`tar czf - /etc \| ssh root@backup "cat > /backups/etc_$(date +%F).tar.gz"`**  
> **Purpose:** Stream‑compress `/etc` and store it remotely.  
> **Details:**  
> - `tar czf - /etc`: gzip tar to stdout  
> - piped into `ssh` to write a dated file on remote  
> - avoids local intermediate archive  

> **`dd if=/dev/sda of=/mnt/usb/drive.img bs=4M status=progress conv=fsync`**  
> **Purpose:** Create a block‑level image of `/dev/sda` with live progress.  
> **Details:**  
> - `bs=4M`: use 4 MiB blocks for speed  
> - `status=progress`: show copy progress  
> - `conv=fsync`: ensure data is flushed to disk  

---

### 📡 Networking & Capture

> **`tcpdump -nn -i eth0 tcp port 80 or port 443 -w ~/captures/web_traffic.pcap`**  
> **Purpose:** Capture raw HTTP/HTTPS traffic on `eth0`.  
> **Details:**  
> - `-nn`: disable name resolution for speed  
> - `-i eth0`: listen on interface `eth0`  
> - filter `tcp port 80 or port 443`  
> - `-w`: write binary PCAP  

> **`nmap -sC -sV -p 1-65535 10.0.0.0/24`**  
> **Purpose:** Run default scripts and version probes on all TCP ports in a subnet.  
> **Details:**  
> - `-sC`: NSE default scripts  
> - `-sV`: service/version detection  
> - `-p 1-65535`: scan entire port range  

> **`ssh -fN -R 9000:localhost:3000 user@remote.server.com`**  
> **Purpose:** Expose your local service on a remote port via reverse SSH tunnel.  
> **Details:**  
> - `-R 9000:localhost:3000`: map remote port 9000 → local 3000  
> - `-fN`: go to background without running remote commands  

---

### ⚙️ System & Logs

> **`journalctl -u nginx.service --since "2025-05-01" --until "2025-05-05 23:59" --no-pager`**  
> **Purpose:** View NGINX logs for a precise date range.  
> **Details:**  
> - `-u nginx.service`: filter by unit name  
> - `--since` / `--until`: time bounds (quotes recommended)  
> - `--no-pager`: output in one shot  

> **`systemctl list-units --failed --no-legend`**  
> **Purpose:** Quickly identify any failed systemd units.  
> **Details:**  
> - `list-units`: show loaded units  
> - `--failed`: only failed ones  
> - `--no-legend`: omit headers/footers  

> **`perf record -g -p $(pidof myapp) && perf report --stdio`**  
> **Purpose:** Profile a running process with call graphs and view a text report.  
> **Details:**  
> - `record -g`: capture call graphs  
> - `-p $(pidof myapp)`: attach to “myapp” PID  
> - `report --stdio`: generate console report  

---

### 🎥 Audio/Video Processing

> **`ffmpeg -i input.mkv -vf "scale=1280:720,fps=30" -c:v libx264 -crf 20 -c:a aac out.mp4`**  
> **Purpose:** Re‑encode a video to 720p @ 30 fps with H.264/AAC.  
> **Details:**  
> - `-vf`: apply filter (scale + framerate)  
> - `-c:v libx264`: choose video codec  
> - `-crf 20`: set quality (lower = higher quality)  
> - `-c:a aac`: choose audio codec  

> **`sox infile.wav outfile.flac rate 48k dither -s`**  
> **Purpose:** Convert WAV to FLAC at 48 kHz with dithering.  
> **Details:**  
> - `rate 48k`: resample to 48 000 Hz  
> - `dither -s`: apply simple triangular dithering  

---

### 🗄️ Compression & Transfer

> **`pv bigfile.iso \| ssh user@remote "cat > ~/bigfile.iso"`**  
> **Purpose:** Copy a large ISO over SSH while seeing progress.  
> **Details:**  
> - `pv`: progress viewer  
> - piped into `ssh` to write remote file  

> **`split -b 100M archive.tar.gz archive.part.`**  
> **Purpose:** Break a large archive into 100 MiB chunks.  
> **Details:**  
> - `-b 100M`: set chunk size  
> - creates `archive.part.aa`, `.ab`, …  
> - reassemble with `cat archive.part.* > archive.tar.gz`
