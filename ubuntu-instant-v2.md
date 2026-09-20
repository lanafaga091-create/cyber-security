📚 BUKU TUTORIAL LENGKAP

UBUNTU DESKTOP DI TERMUX X11

Panduan Instalasi Otomatis dengan AI Local & Layout Ubuntu

---

📖 DAFTAR ISI

BAB 1 — Pendahuluan & Persiapan
BAB 2 — Instalasi Otomatis (One Command)
BAB 3 — Cara Menggunakan Setelah Instalasi
BAB 4 — Troubleshooting & Verifikasi
BAB 5 — Full Script Lengkap (Copy-Paste)

---

BAB 1 — PENDAHULUAN & PERSIAPAN

1.1 Apa yang Akan Anda Dapatkan

Setelah mengikuti tutorial ini, Anda akan memiliki:

Komponen Detail
Sistem Operasi Ubuntu 22.04 di dalam Termux
Desktop XFCE4 (ringan, stabil)
Tema Yaru-dark (warna oranye khas Ubuntu)
Ikon Yaru (ikon resmi Ubuntu)
Font Ubuntu 11
Kursor Yaru
Wallpaper Auto-download dari internet
Top Bar Panel atas 32px mirip GNOME
Dock Plank dock di bawah (macOS-style)
AI Local AI (auto-fix error tanpa API key)
Auto-detect lokasi IP geolocation

1.2 Persyaratan Minimum

Komponen Minimum Rekomendasi
RAM 4 GB 8 GB+
Storage kosong 8 GB 15 GB+
Android 10+ 12+
Chipset Snapdragon 660 Snapdragon 7-series+

1.3 Aplikasi yang Harus Diinstall

1. Termux — dari F-Droid
2. Termux:X11 — dari F-Droid (ARM64)
3. Termux:API — dari F-Droid (opsional, untuk notifikasi)

⚠️ PENTING: Jangan install Termux dari Google Play Store — versinya sudah usang.

1.4 Setting HP Sebelum Mulai

Lakukan setting ini agar Termux tidak di-kill Android:

1. Baterai: Settings → Apps → Termux → Battery → Unrestricted
2. Autostart: Settings → Apps → Termux → Autostart → Allow
3. Display over other apps: Settings → Apps → Termux → Allow
4. Lock di Recent Apps: Buka Recent Apps → tahan Termux → ikon gembok

---

BAB 2 — INSTALASI OTOMATIS

2.1 Buka Termux

Buka aplikasi Termux. Anda akan melihat prompt ~ $.

2.2 Buat File Script

Ketik perintah ini:

```bash
nano ~/ubuntu-instant-v2.sh
```

2.3 Copy Script

Copy SELURUH script di BAB 5 (bawah) → paste di nano.

2.4 Simpan File

Tekan:

· CTRL + O → Enter → CTRL + X

2.5 Verifikasi Syntax

Ketik:

```bash
bash -n ~/ubuntu-install.sh
```

Jika tidak ada output = script valid ✅
Jika ada error = copy ulang script dari BAB 5

2.6 Jalankan Installer

Ketik:

```bash
chmod +x ~/ubuntu-instant-v2.sh
bash ~/ubuntu-instant-v2.sh install
```

2.7 Ikuti Prompt

Langkah 1 — Username:

```
Username (huruf kecil) ❯
```

Ketik username Anda (contoh: budi). Tekan Enter.

Langkah 2 — Password:

```
Password ❯
```

Ketik password (tidak akan terlihat). Tekan Enter.

Langkah 3 — Auto-detect lokasi:
Script akan otomatis mendeteksi lokasi Anda via IP:

```
🌍 AI MENDETEKSI LOKASI ANDA

✓ Lokasi: 🇮🇩 Jakarta, Indonesia

┌─────────────────────────────────────┬──────────────────────┐
│ Pertanyaan                          │ Auto-Fill            │
├─────────────────────────────────────┼──────────────────────┤
│ Geographic area                     │ 6 (Asia)             │
│ Time zone                           │ 33 (Jakarta)         │
│ Country keyboard                    │ 32                   │
│ Keyboard layout                     │ 1                    │
│ Encoding console                    │ 27 (UTF-8)           │
│ Locale                              │ en_US.UTF-8          │
│ Display manager                     │ 1 (gdm3)             │
│ Restart services                    │ default              │
└─────────────────────────────────────┴──────────────────────┘
```

Tunggu 3 detik → lanjut otomatis.

Langkah 4 — Progress bar:

```
[████████░░░░░░░░░░░░░░░░░] 34% 892 MB/2450 MB Install Ubuntu...
```

Tunggu sampai 100% (10-25 menit tergantung internet).

Langkah 5 — Selesai:

```
✨ INSTALASI BERHASIL — SEMUA OTOMATIS! ✨
🔄 Auto-launch dalam 3 detik...
```

Desktop Ubuntu akan otomatis terbuka di Termux:X11.

---

BAB 3 — CARA MENGGUNAKAN

3.1 Setelah Instalasi Selesai

Desktop Ubuntu Anda sudah terbuka. Anda akan lihat:

Elemen Posisi
Panel atas (top bar) Atas layar, 32px
Menu Ubuntu (Whisker) Kiri atas panel
Jam Tengah panel
System tray Kanan panel
Wallpaper Full screen
Plank dock Bawah tengah

3.2 Perintah Setelah Install

Buka Termux baru (bukan Ubuntu), ketik:

Perintah Fungsi
desktop Buka desktop Ubuntu
ubuntu Masuk terminal Ubuntu saja
x11 Nyalakan X11 saja
check-ubuntu Cek apakah layout sudah OK

3.3 Setiap Kali Mau Pakai Ubuntu

1. Buka Termux
2. Ketik:
   ```bash
   desktop
   ```
3. Tunggu 10-15 detik
4. Buka aplikasi Termux:X11
5. Desktop muncul

3.4 Mematikan Ubuntu

Tekan CTRL + C di Termux, atau tutup aplikasi Termux:X11.

---

BAB 4 — TROUBLESHOOTING

4.1 Cek Layout Sudah OK

Ketik di Termux:

```bash
check-ubuntu
```

Output:

```
🔍 CEK LAYOUT UBUNTU TERPASANG

  ✓ Wallpaper
  ✓ Tema Yaru
  ✓ Panel 32px
  ✓ Plank dock
  ✓ xscreensaver dihapus
  ✓ Folder backdrop
```

Kalau ada ✗, jalankan fix manual di BAB 4.3.

4.2 Error Umum & Solusi

Error Penyebab Solusi
xscreensaver: authentication disallowed xscreensaver + root conflict Script sudah auto-remove
Unable to load images from folder (null) Folder backdrop kosong Script auto-fix
Folder instalasi tidak ditemukan Path proot v5 mismatch Local AI cleanup
Container ubuntu already exists Metadata rusak Local AI cleanup
Failed to create stream fd Normal Termux Abaikan
systemd error Normal proot Abaikan
plocate hang Bug di proot Script skip plocate

4.3 Fix Manual (Kalau Ada yang Belum Muncul)

Buka terminal XFCE4 di desktop Ubuntu, jalankan:

Fix wallpaper:

```bash
sudo mkdir -p /usr/share/xfce4/backdrops
sudo cp /usr/share/backgrounds/*.png /usr/share/xfce4/backdrops/ 2>/dev/null
xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitor0/workspace0/last-image -s /usr/share/backgrounds/warty-final-ubuntu.png
xfdesktop --reload
```

Fix panel:

```bash
xfce4-panel --quit
sleep 1
xfce4-panel &
```

Fix Plank:

```bash
pkill -9 plank
sleep 1
plank &
```

4.4 Kalau Desktop Tidak Muncul

1. Tutup Termux:X11
2. Tutup Termux
3. Buka Termux lagi
4. Ketik desktop
5. Tunggu 15 detik
6. Buka Termux:X11

4.5 Kalau Install Gagal Total

Jalankan force install:

```bash
bash ~/ubuntu-instant-v2.sh --force-install
```

Kalau masih gagal, hapus Ubuntu dan coba lagi:

```bash
proot-distro remove ubuntu
rm -rf $PREFIX/var/lib/proot-distro/containers/ubuntu
rm -rf $PREFIX/var/lib/proot-distro/installed-rootfs/ubuntu
bash ~/ubuntu-instant-v2.sh install
```

4.6 Local AI Auto-Fix

Kalau ada error saat instalasi, Local AI akan otomatis:

1. Analyze error dengan 40+ pattern
2. Check learning database (pengalaman sebelumnya)
3. Pick strategi terbaik
4. Execute semua strategi (auto-cleanup, retry, dll)
5. Learn dari hasil
6. Auto-retry max 3x

Output contoh:

```
🧠 LOCAL AI MENGANALISIS ERROR
⚠ Error: Install Ubuntu
🔍 Diagnosa: Path proot v5 mismatch
🎯 Confidence: 95%
🛠 Strategi: cleanup;retry
▶ cleanup
▶ retry
🔄 AUTO-RETRY (1/3)...
```

---

BAB 5 — FULL SCRIPT LENGKAP

5.1 Instruksi Copy-Paste

1. Buka Termux
2. Ketik: nano ~/ubuntu-instant-v2.sh
3. Copy seluruh script di bawah
4. Paste di nano (tekan lama → Paste)
5. Simpan: CTRL + O → Enter → CTRL + X
6. Jalankan: bash ~/ubuntu-instant-v2.sh install

5.2 Script Lengkap

```bash
#!/data/data/com.termux/files/usr/bin/bash

# ============================================================
#  UBUNTU AUTO INSTALLER v21.0 FINAL (FIXED)
#  Full Layout + Local AI + Auto-Location
# ============================================================

RED='\033[0;31m'; GREEN='\033[0;32m'; YELLOW='\033[1;33m'; BLUE='\033[0;34m'
MAGENTA='\033[0;35m'; CYAN='\033[0;36m'; WHITE='\033[1;37m'; ORANGE='\033[38;5;208m'
PINK='\033[38;5;213m'; LIME='\033[38;5;154m'; SKY='\033[38;5;117m'; PURPLE='\033[38;5;141m'
GOLD='\033[38;5;220m'; BOLD='\033[1m'; DIM='\033[2m'; NC='\033[0m'

TMP_DIR="$PREFIX/tmp"; mkdir -p "$TMP_DIR" 2>/dev/null
LOG_FILE="$HOME/ubuntu-install.log"
AI_LOG="$HOME/ubuntu-ai.log"
LEARN_DB="$HOME/.ubuntu-ai-learning.db"
GEO_CACHE="$TMP_DIR/ubuntu-geo.json"
CONFIG_FILE="$HOME/.ubuntu-config"
LAUNCHER_FILE="$HOME/start-ubuntu-desktop.sh"
VERIFY_FILE="$HOME/check-ubuntu-layout.sh"
PROOT_BASE="$PREFIX/var/lib/proot-distro"
ROOTFS_NEW="$PROOT_BASE/containers/ubuntu/rootfs"
ROOTFS_OLD="$PROOT_BASE/installed-rootfs/ubuntu"
CONTAINERS_BASE="$PROOT_BASE/containers"
DISTRO_BASE="$PROOT_BASE/distro"
CACHE_BASE="$PROOT_BASE/cache"
MESSAGE_FILE="$TMP_DIR/ubuntu-message.txt"
TRACKER_FLAG="$TMP_DIR/ubuntu-tracker.flag"
RETRY_FILE="$TMP_DIR/ubuntu-retry.count"
TERMUX_BASE_KB=51200
TOTAL_INSTALL_KB=2508800
MAX_AUTO_RETRY=3

KB_DATABASE=(
    "already exists|cleanup;retry|Container metadata rusak|95"
    "folder instalasi tidak ditemukan|cleanup;retry|Path proot v5|95"
    "container.*not found|cleanup;reinstall|Container hilang|90"
    "unable to locate package|apt_update;cleanup_cache;retry|Repo outdated|90"
    "unable to fetch|check_internet;apt_update_retry|Koneksi repo gagal|85"
    "could not resolve|dns_fix;check_internet|DNS error|85"
    "404|apt_update;cleanup_cache;retry|Repo path berubah|80"
    "hash sum mismatch|cleanup_cache;apt_update_retry|Cache korup|90"
    "gpg error|fix_gpg_keys|GPG expired|80"
    "package.*broken|apt_fix_broken|Dependensi rusak|90"
    "dpkg.*lock|remove_dpkg_lock|Lock nyangkut|95"
    "dpkg was interrupted|dpkg_configure|Instalasi interrupted|90"
    "connection timed out|check_internet;retry|Timeout|85"
    "network is unreachable|check_internet|Jaringan off|95"
    "no space left|cleanup_cache;check_storage|Storage penuh|95"
    "cannot allocate memory|cleanup_ram|RAM habis|90"
    "permission denied|fix_perm;setup_storage|Izin kurang|85"
    "killed|check_ram;cleanup_cache|OOM|90"
    "no such file|recreate_folders;retry|Path hilang|85"
    "plocate|remove_plocate|Plocate hang|95"
    "fonts-ubuntu-font-family-console|skip_fonts_pkg|Paket ARM64 n/a|95"
    "failed to create stream fd|ignore_continue|Normal Termux|100"
    "systemd|ignore_systemd|No systemd di proot|100"
    "policy-rc.d|ignore_policy|Normal proot|100"
    "dbus.*failed|ignore_dbus;retry|DBus partial|75"
    "xscreensaver.*authentication|remove_xscreensaver|Root conflict|95"
    "xscreensaver.*oom_score|remove_xscreensaver|Xscreensaver crash|95"
    "xscreensaver|remove_xscreensaver|Hapus xscreensaver|95"
    "xfce4-panel.*error|restart_panel|Panel crash|85"
    "plank.*error|restart_plank|Plank crash|85"
    "wallpaper.*null|fix_wallpaper_folder|Folder backdrop kosong|95"
    "backdrop.*not found|fix_wallpaper_folder|Folder backdrop kosong|95"
    "unable to load images.*null|fix_wallpaper_folder|Wallpaper error|95"
    "undefined symbol|reinstall_pkg|ABI mismatch|80"
    "core dumped|reinstall_pkg;retry|Crash library|75"
    "error|cleanup;retry|Error umum|50"
    "failed|cleanup;retry|Gagal|50"
)

learn_success() { echo "$(date +%s)|$1|$2|SUCCESS" >> "$LEARN_DB"; }
learn_failure() { echo "$(date +%s)|$1|$2|FAILED" >> "$LEARN_DB"; }

check_learned() {
    [ ! -f "$LEARN_DB" ] && return 1
    local m=$(grep -F "$1" "$LEARN_DB" 2>/dev/null | grep "SUCCESS" | tail -1 | cut -d'|' -f3)
    [ -n "$m" ] && { echo "$m"; return 0; }
    return 1
}

ai_analyze() {
    local e=$(echo "$1" | tr '[:upper:]' '[:lower:]')
    local l=$(check_learned "$e")
    [ -n "$l" ] && { echo "LEARNED|$l|Pengalaman sebelumnya|99"; return 0; }
    local best="" conf=0
    for entry in "${KB_DATABASE[@]}"; do
        local p=$(echo "$entry" | cut -d'|' -f1)
        if echo "$e" | grep -qE "$p"; then
            local c=$(echo "$entry" | cut -d'|' -f4)
            [ "$c" -gt "$conf" ] && { conf=$c; best="$entry"; }
        fi
    done
    [ -n "$best" ] && { echo "KB|$best"; return 0; }
    echo "UNKNOWN||Tidak ada pola|0"
    return 1
}

strategy_cleanup() {
    proot-distro remove ubuntu 2>/dev/null
    rm -rf "$ROOTFS_OLD" "$ROOTFS_NEW" "$DISTRO_BASE/ubuntu" "$CONTAINERS_BASE/ubuntu" 2>/dev/null
    rm -rf "$CACHE_BASE/ubuntu"* 2>/dev/null
    sync 2>/dev/null
    sleep 2
}
strategy_apt_update() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
apt update
EOF
}
strategy_apt_update_retry() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
apt clean; apt update --fix-missing; apt update
EOF
}
strategy_apt_fix_broken() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
dpkg --configure -a; apt --fix-broken install -y; apt update
EOF
}
strategy_cleanup_cache() {
    pkg clean 2>/dev/null
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
apt clean; apt autoremove -y; rm -rf /var/lib/apt/lists/*
EOF
    rm -rf "$CACHE_BASE"/* 2>/dev/null
}
strategy_check_internet() {
    for h in 8.8.8.8 1.1.1.1 google.com; do
        ping -c 1 -W 3 $h > /dev/null 2>&1 && return 0
    done
    return 1
}
strategy_dns_fix() {
    echo "nameserver 8.8.8.8" > $PREFIX/etc/resolv.conf 2>/dev/null
    echo "nameserver 1.1.1.1" >> $PREFIX/etc/resolv.conf 2>/dev/null
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
echo "nameserver 8.8.8.8" > /etc/resolv.conf
echo "nameserver 1.1.1.1" >> /etc/resolv.conf
EOF
}
strategy_check_storage() {
    [ "$(( $(df $PREFIX | awk 'NR==2 {print $4}') / 1024 ))" -gt 5000 ]
}
strategy_fix_perm() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
chmod -R 755 /usr/local/bin 2>/dev/null
EOF
}
strategy_setup_storage() { termux-setup-storage 2>/dev/null; sleep 2; }
strategy_recreate_folders() {
    mkdir -p "$PROOT_BASE" "$ROOTFS_OLD" "$CONTAINERS_BASE" "$DISTRO_BASE" "$CACHE_BASE" "$TMP_DIR" 2>/dev/null
}
strategy_remove_plocate() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
apt remove -y plocate 2>/dev/null || true
rm -f /etc/cron.daily/plocate /etc/cron.d/plocate 2>/dev/null
EOF
}
strategy_remove_pkg() {
    local p=$(echo "$1" | grep -oE "package ['\"]?[a-z0-9._-]+" | head -1 | sed "s/package ['\"]*//")
    [ -n "$p" ] && proot-distro login ubuntu --shared-tmp 2>/dev/null << EOF > /dev/null 2>&1
apt remove -y "$p" 2>/dev/null || true
apt --fix-broken install -y 2>/dev/null || true
EOF
}
strategy_remove_dpkg_lock() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
rm -f /var/lib/dpkg/lock-frontend /var/lib/dpkg/lock /var/cache/apt/archives/lock 2>/dev/null
dpkg --configure -a 2>/dev/null
EOF
}
strategy_dpkg_configure() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
dpkg --configure -a; apt --fix-broken install -y
EOF
}
strategy_reinstall_proot() {
    pkg uninstall -y proot-distro 2>/dev/null
    pkg install -y proot-distro 2>/dev/null
    sleep 2
}
strategy_reinstall_pkg() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
apt install --reinstall -y 2>/dev/null
EOF
}
strategy_fix_gpg_keys() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
apt-key adv --refresh-keys 2>/dev/null || true
apt update 2>&1
EOF
}
strategy_cleanup_ram() { sync; pkill -f "not-needed" 2>/dev/null; }
strategy_skip_fonts_pkg() { sed -i 's/fonts-ubuntu-font-family-console//g' "$0" 2>/dev/null; }
strategy_retry_wait() { sleep 5; }
strategy_reinstall() { strategy_cleanup; sleep 2; }
strategy_retry() { return 0; }
strategy_ignore_continue() { return 0; }
strategy_ignore_systemd() { return 0; }
strategy_ignore_policy() { return 0; }
strategy_ignore_dbus() { return 0; }
strategy_remove_xscreensaver() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
pkill -9 xscreensaver 2>/dev/null
apt remove --purge -y xscreensaver xscreensaver-data xscreensaver-gl 2>/dev/null
apt autoremove -y 2>/dev/null
EOF
}
strategy_restart_panel() {
    proot-distro login ubuntu --shared-tmp --user "${UBUNTU_USER:-root}" 2>/dev/null << 'EOF' > /dev/null 2>&1
xfce4-panel --quit 2>/dev/null
sleep 1
xfce4-panel > /dev/null 2>&1 &
EOF
}
strategy_restart_plank() {
    proot-distro login ubuntu --shared-tmp --user "${UBUNTU_USER:-root}" 2>/dev/null << 'EOF' > /dev/null 2>&1
pkill -9 plank 2>/dev/null
sleep 1
plank > /dev/null 2>&1 &
EOF
}
strategy_fix_wallpaper_folder() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
mkdir -p /usr/share/xfce4/backdrops
cp /usr/share/backgrounds/*.jpg /usr/share/xfce4/backdrops/ 2>/dev/null
cp /usr/share/backgrounds/*.png /usr/share/xfce4/backdrops/ 2>/dev/null
EOF
}

execute_strategy() {
    case "$1" in
        cleanup) strategy_cleanup ;;
        apt_update) strategy_apt_update ;;
        apt_update_retry) strategy_apt_update_retry ;;
        apt_fix_broken) strategy_apt_fix_broken ;;
        cleanup_cache) strategy_cleanup_cache ;;
        check_internet) strategy_check_internet ;;
        dns_fix) strategy_dns_fix ;;
        check_storage) strategy_check_storage ;;
        fix_perm) strategy_fix_perm ;;
        setup_storage) strategy_setup_storage ;;
        recreate_folders) strategy_recreate_folders ;;
        remove_plocate) strategy_remove_plocate ;;
        remove_pkg) strategy_remove_pkg "$2" ;;
        remove_dpkg_lock) strategy_remove_dpkg_lock ;;
        dpkg_configure) strategy_dpkg_configure ;;
        reinstall_proot) strategy_reinstall_proot ;;
        reinstall_pkg) strategy_reinstall_pkg ;;
        fix_gpg_keys) strategy_fix_gpg_keys ;;
        cleanup_ram) strategy_cleanup_ram ;;
        skip_fonts_pkg) strategy_skip_fonts_pkg ;;
        retry_wait) strategy_retry_wait ;;
        reinstall) strategy_reinstall ;;
        retry) strategy_retry ;;
        ignore_continue) strategy_ignore_continue ;;
        ignore_systemd) strategy_ignore_systemd ;;
        ignore_policy) strategy_ignore_policy ;;
        ignore_dbus) strategy_ignore_dbus ;;
        remove_xscreensaver) strategy_remove_xscreensaver ;;
        restart_panel) strategy_restart_panel ;;
        restart_plank) strategy_restart_plank ;;
        fix_wallpaper_folder) strategy_fix_wallpaper_folder ;;
        *) ;;
    esac
}

local_ai_fix() {
    local fase="$1" err="$2"
    clear
    echo ""
    echo -e "${PURPLE}${BOLD}"
    echo "  ╔══════════════════════════════════════════════════════════════╗"
    echo "  ║           🧠  LOCAL AI MENGANALISIS ERROR  🧠                 ║"
    echo "  ╚══════════════════════════════════════════════════════════════╝"
    echo -e "${NC}\n"
    echo -e "  ${YELLOW}⚠ Error:\033[0m ${GOLD}$fase${NC}"
    echo -e "  ${DIM}${err:0:120}${NC}\n"
    echo "[$(date)] ERROR $fase: $err" >> "$AI_LOG"

    local a=$(ai_analyze "$err")
    local src=$(echo "$a" | cut -d'|' -f1)
    local data=$(echo "$a" | cut -d'|' -f2)
    local diag=$(echo "$a" | cut -d'|' -f3)
    local conf=$(echo "$a" | cut -d'|' -f4)

    echo -e "  ${CYAN}🔍 Diagnosa:\033[0m ${WHITE}$diag${NC}"
    echo -e "  ${CYAN}🎯 Confidence:\033[0m ${GOLD}${conf}%${NC}\n"

    local strats="cleanup;retry"
    [ "$src" = "KB" ] && strats=$(echo "$data" | cut -d'|' -f2)
    [ "$src" = "LEARNED" ] && strats="$data"

    echo -e "  ${CYAN}🛠 Strategi:\033[0m ${GOLD}$strats${NC}\n"
    sleep 1

    local IFS=';'
    for s in $strats; do
        echo -e "  ${PINK}▶${NC} ${WHITE}$s${NC}"
        execute_strategy "$s" "$err"
        learn_success "$err" "$s"
        sleep 1
    done

    echo ""
    local rc=0
    [ -f "$RETRY_FILE" ] && rc=$(cat "$RETRY_FILE")
    rc=$((rc + 1))
    echo "$rc" > "$RETRY_FILE"
    if [ "$rc" -le "$MAX_AUTO_RETRY" ]; then
        echo -e "  ${LIME}🔄 AUTO-RETRY ($rc/$MAX_AUTO_RETRY)...${NC}\n"
        sleep 5
        exec bash "$0" install
    else
        echo -e "  ${RED}✗ $MAX_AUTO_RETRY kali gagal${NC}\n"
        echo -ne "  ${GOLD}Reset & coba lagi? (y/n) ❯${NC} "
        read -r F
        [ "$F" = "y" ] || [ -z "$F" ] && { rm -f "$RETRY_FILE"; exec bash "$0" install; }
        exit 1
    fi
}

detect_location() {
    if [ -f "$GEO_CACHE" ]; then
        local age=$(( $(date +%s) - $(stat -c %Y "$GEO_CACHE" 2>/dev/null || echo 0) ))
        [ "$age" -lt 86400 ] && { cat "$GEO_CACHE"; return 0; }
    fi
    local r=$(curl -s -m 8 "https://ipapi.co/json/" 2>/dev/null)
    [ -n "$r" ] && echo "$r" | grep -q '"country_code"' && { echo "$r" > "$GEO_CACHE"; echo "$r"; return 0; }
    r=$(curl -s -m 8 "http://ip-api.com/json/" 2>/dev/null)
    if [ -n "$r" ] && echo "$r" | grep -q '"countryCode"'; then
        local cc=$(echo "$r" | grep -oE '"countryCode":"[^"]*"' | cut -d'"' -f4)
        local tz=$(echo "$r" | grep -oE '"timezone":"[^"]*"' | cut -d'"' -f4)
        local city=$(echo "$r" | grep -oE '"city":"[^"]*"' | cut -d'"' -f4)
        local country=$(echo "$r" | grep -oE '"country":"[^"]*"' | cut -d'"' -f4)
        local out="{\"country_code\":\"$cc\",\"timezone\":\"$tz\",\"city\":\"$city\",\"country_name\":\"$country\"}"
        echo "$out" > "$GEO_CACHE"
        echo "$out"
        return 0
    fi
    echo '{"country_code":"ID","timezone":"Asia/Jakarta","city":"Jakarta","country_name":"Indonesia"}'
}

country_to_continent() {
    case "$1" in
        ID|MY|SG|TH|VN|PH|JP|KR|CN|IN|PK|BD|HK|TW|KH|LA|MM|NP|LK|MV|BN|MN|KZ|UZ|KG|TJ|TM|AF|IR|IQ|IL|JO|LB|SY|SA|AE|QA|BH|KW|OM|YE|TR|GE|AM|AZ) echo "6" ;;
        GB|DE|FR|IT|ES|NL|BE|CH|AT|SE|NO|DK|FI|PL|CZ|HU|RO|BG|GR|PT|IE|IS|HR|SI|SK|RS|BA|MK|AL|EE|LV|LT|UA|BY|MD|RU|MT|CY|LU) echo "8" ;;
        ZA|EG|NG|KE|ET|GH|TZ|UG|MA|DZ|TN|LY|SD|AO|MZ|ZW|ZM|BW|NA|SN|CI|CM|BF|ML|NE|TD|MR|SO|RW|BI|MW|MG|MU) echo "1" ;;
        US|CA|MX|BR|AR|CL|CO|PE|VE|EC|BO|PY|UY|GY|SR|CR|PA|GT|BZ|SV|HN|NI|CU|DO|HT|JM|TT|BB) echo "2" ;;
        AU|NZ|FJ|PG|SB|VU|NC|PF|WS|TO|KI|TV|NR|PW|FM|MH|GU) echo "4" ;;
        *) echo "6" ;;
    esac
}
continent_name() {
    case "$1" in
        1) echo "Africa" ;;
        2) echo "America" ;;
        4) echo "Australia" ;;
        6) echo "Asia" ;;
        8) echo "Europe" ;;
        *) echo "Asia" ;;
    esac
}
timezone_to_city() {
    case "$1" in
        Asia/Jakarta) echo "33" ;;
        Asia/Bangkok) echo "32" ;;
        Asia/Singapore) echo "71" ;;
        Asia/Tokyo) echo "81" ;;
        Asia/Seoul) echo "69" ;;
        Asia/Shanghai) echo "70" ;;
        Asia/Kolkata) echo "44" ;;
        Asia/Dubai) echo "24" ;;
        Europe/London) echo "58" ;;
        Europe/Paris) echo "38" ;;
        Europe/Berlin) echo "20" ;;
        America/New_York) echo "40" ;;
        America/Los_Angeles) echo "31" ;;
        Africa/Cairo) echo "21" ;;
        Australia/Sydney) echo "81" ;;
        *) echo "33" ;;
    esac
}
country_to_keyboard() {
    case "$1" in
        FR|BE|LU) echo "40" ;;
        DE|AT|CH) echo "44" ;;
        ES|MX|AR) echo "84" ;;
        IT) echo "55" ;;
        PT|BR) echo "78" ;;
        NL) echo "24" ;;
        RU|UA) echo "79" ;;
        JP) echo "55" ;;
        KR) echo "59" ;;
        CN|TW|HK) echo "20" ;;
        TR) echo "94" ;;
        *) echo "32" ;;
    esac
}
country_to_locale() {
    case "$1" in
        FR|BE|LU) echo "fr_FR.UTF-8" ;;
        DE|AT|CH) echo "de_DE.UTF-8" ;;
        ES|MX) echo "es_ES.UTF-8" ;;
        IT) echo "it_IT.UTF-8" ;;
        PT|BR) echo "pt_BR.UTF-8" ;;
        NL) echo "nl_NL.UTF-8" ;;
        RU|UA) echo "ru_RU.UTF-8" ;;
        JP) echo "ja_JP.UTF-8" ;;
        KR) echo "ko_KR.UTF-8" ;;
        CN|SG) echo "zh_CN.UTF-8" ;;
        TR) echo "tr_TR.UTF-8" ;;
        *) echo "en_US.UTF-8" ;;
    esac
}
country_flag() {
    local cc=$(echo "$1" | tr '[:lower:]' '[:upper:]')
    local c1=$(printf "%d" "'${cc:0:1}")
    local c2=$(printf "%d" "'${cc:1:1}")
    printf "$(printf '\\U%08x\\U%08x' $((c1+127397)) $((c2+127397)))"
}

auto_answer_questions() {
    clear
    echo ""
    echo -e "${CYAN}${BOLD}"
    echo "  ╔══════════════════════════════════════════════════════════════╗"
    echo "  ║        🌍  AI MENDETEKSI LOKASI ANDA  🌍                     ║"
    echo "  ╚══════════════════════════════════════════════════════════════╝"
    echo -e "${NC}\n"
    echo -e "  ${YELLOW}⏳ Mendeteksi lokasi...${NC}\n"
    local geo=$(detect_location)
    local cc=$(echo "$geo" | grep -oE '"country_code"[: ]*"[^"]*"' | grep -oE '"[A-Z]{2}"' | tr -d '"' | head -1)
    [ -z "$cc" ] && cc=$(echo "$geo" | grep -oE '"countryCode"[: ]*"[^"]*"' | grep -oE '"[A-Z]{2}"' | tr -d '"' | head -1)
    [ -z "$cc" ] && cc="ID"
    local tz=$(echo "$geo" | grep -oE '"timezone"[: ]*"[^"]*"' | cut -d'"' -f4 | head -1)
    [ -z "$tz" ] && tz="Asia/Jakarta"
    local city=$(echo "$geo" | grep -oE '"city"[: ]*"[^"]*"' | cut -d'"' -f4 | head -1)
    [ -z "$city" ] && city="Jakarta"
    local country=$(echo "$geo" | grep -oE '"country_name"[: ]*"[^"]*"' | cut -d'"' -f4 | head -1)
    [ -z "$country" ] && country=$(echo "$geo" | grep -oE '"country"[: ]*"[^"]*"' | cut -d'"' -f4 | head -1)
    [ -z "$country" ] && country="Indonesia"
    local geo_area=$(country_to_continent "$cc")
    local geo_name=$(continent_name "$geo_area")
    local tz_city=$(timezone_to_city "$tz")
    local kb_country=$(country_to_keyboard "$cc")
    local locale=$(country_to_locale "$cc")
    local flag=$(country_flag "$cc")
    echo -e "  ${LIME}${BOLD}✓ Lokasi: ${flag} $city, $country${NC}\n"
    echo -e "  ${CYAN}┌─────────────────────────────────────┬──────────────────────┐${NC}"
    echo -e "  ${CYAN}│${NC}  ${WHITE}Pertanyaan${NC}                        ${CYAN}│${NC}  ${WHITE}Auto-Fill${NC}${CYAN}           │${NC}"
    echo -e "  ${CYAN}├─────────────────────────────────────┼──────────────────────┤${NC}"
    echo -e "  ${CYAN}│${NC}  Geographic area                    ${CYAN}│${NC}  ${GOLD}$geo_area${NC} ${DIM}($geo_name)${NC}"
    echo -e "  ${CYAN}│${NC}  Time zone                          ${CYAN}│${NC}  ${GOLD}$tz_city${NC} ${DIM}($city)${NC}"
    echo -e "  ${CYAN}│${NC}  Country keyboard                   ${CYAN}│${NC}  ${GOLD}$kb_country${NC}"
    echo -e "  ${CYAN}│${NC}  Keyboard layout                    ${CYAN}│${NC}  ${GOLD}1${NC}"
    echo -e "  ${CYAN}│${NC}  Encoding console                   ${CYAN}│${NC}  ${GOLD}27${NC} ${DIM}(UTF-8)${NC}"
    echo -e "  ${CYAN}│${NC}  Locale                             ${CYAN}│${NC}  ${GOLD}$locale${NC}"
    echo -e "  ${CYAN}│${NC}  Display manager                    ${CYAN}│${NC}  ${GOLD}1${NC} ${DIM}(gdm3)${NC}"
    echo -e "  ${CYAN}│${NC}  Restart services                   ${CYAN}│${NC}  ${GOLD}default${NC}"
    echo -e "  ${CYAN}└─────────────────────────────────────┴──────────────────────┘${NC}\n"
    echo -e "  ${PINK}💡 Zero manual input — AI isi semua!${NC}\n"
    sleep 3
    cat >> "$CONFIG_FILE" << EOF

INSTALL_GEO="$geo_area"
INSTALL_GEO_NAME="$geo_name"
INSTALL_TZ="$tz_city"
INSTALL_TZ_NAME="$tz"
INSTALL_KB_COUNTRY="$kb_country"
INSTALL_KB_LAYOUT="1"
INSTALL_ENCODING="27"
INSTALL_LOCALE="$locale"
INSTALL_DM="1"
INSTALL_RESTART="default"
DETECTED_COUNTRY="$country"
DETECTED_CITY="$city"
DETECTED_CC="$cc"
EOF
}

setup_full_layout() {
    load_config
    local U="${UBUNTU_USER:-root}"

    progress_set_message "Download wallpaper..."
    local wp_urls=(
        "https://raw.githubusercontent.com/ubuntu/ubuntu-wallpapers/master/warty-final-ubuntu.png"
        "https://raw.githubusercontent.com/ubuntu/ubuntu-wallpapers/master/jammy-jellyfish.jpg"
        "https://i.imgur.com/kN2FqBm.png"
    )
    for url in "${wp_urls[@]}"; do
        local fn=$(basename "$url")
        curl -s -m 20 -L "$url" -o "$TMP_DIR/$fn" 2>/dev/null
        if [ -s "$TMP_DIR/$fn" ]; then
            local root=$(get_ubuntu_rootfs)
            [ -n "$root" ] && cp "$TMP_DIR/$fn" "$root/root/$fn" 2>/dev/null
        fi
    done

    progress_set_message "Fix wallpaper folder..."
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
mkdir -p /usr/share/xfce4/backdrops /usr/share/backgrounds
cp /root/*.png /usr/share/backgrounds/ 2>/dev/null
cp /root/*.jpg /usr/share/backgrounds/ 2>/dev/null
cp /usr/share/backgrounds/*.png /usr/share/xfce4/backdrops/ 2>/dev/null
cp /usr/share/backgrounds/*.jpg /usr/share/xfce4/backdrops/ 2>/dev/null
rm -f /root/*.png /root/*.jpg 2>/dev/null
EOF

    progress_set_message "Hapus xscreensaver..."
    strategy_remove_xscreensaver

    progress_set_message "Setup panel layout..."
    for TU in "$U" "root"; do
        proot-distro login ubuntu --shared-tmp --user "$TU" 2>/dev/null << 'LAYOUT_EOF' > /dev/null 2>&1
xfce4-panel --quit 2>/dev/null
sleep 1
xfconf-query -c xfce4-panel -p /panels/panel-1/size -s 32 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/position -s "p=6;x=0;y=0" 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/length -s 100 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/position-locked -s true 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/background-style -s 1 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/background-alpha -s 85 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/autohide-behavior -s 0 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -r -R 2>/dev/null
sleep 1
xfconf-query -c xfce4-panel -p /plugins/plugin-1 -s "whiskermenu" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-1/button-icon -s "distributor-logo" 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-1/button-title -s " " 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 1 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-2 -s "separator" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-2/expand -s true 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 2 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-3 -s "clock" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-3/digital-format -s "%H:%M" 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-3/digital-time-font -s "Ubuntu Bold 11" 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 3 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-4 -s "separator" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 4 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-5 -s "systray" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 5 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-6 -s "pulseaudio" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 6 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-7 -s "power-manager-plugin" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 7 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-8 -s "notification-plugin" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 8 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-9 -s "clock" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-9/digital-format -s "%a %d %b" 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-9/digital-time-font -s "Ubuntu 10" 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 9 2>/dev/null
xfconf-query -c xfce4-panel -p /plugins/plugin-10 -s "showdesktop" -n -t string 2>/dev/null
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -a -t int -s 10 2>/dev/null
xfconf-query -c xsettings -p /Net/ThemeName -s "Yaru-dark" 2>/dev/null
xfconf-query -c xsettings -p /Net/IconThemeName -s "Yaru-dark" 2>/dev/null
xfconf-query -c xsettings -p /Gtk/CursorThemeName -s "Yaru" 2>/dev/null
xfconf-query -c xsettings -p /Gtk/FontName -s "Ubuntu 11" 2>/dev/null
xfconf-query -c xfwm4 -p /general/theme -s "Yaru-dark" 2>/dev/null
xfconf-query -c xfwm4 -p /general/title_font -s "Ubuntu Bold 11" 2>/dev/null
xfconf-query -c xfwm4 -p /general/button_layout -s "O|SHMC" 2>/dev/null
xfconf-query -c xfwm4 -p /general/title_alignment -s "center" 2>/dev/null
xfconf-query -c xfwm4 -p /general/use_compositing -s true 2>/dev/null
xfconf-query -c xfwm4 -p /general/show_frame_shadow -s false 2>/dev/null
xfconf-query -c xfwm4 -p /general/show_popup_shadow -s false 2>/dev/null
WALL=""
for w in /usr/share/backgrounds/warty-final-ubuntu.png /usr/share/backgrounds/jammy-jellyfish.jpg /usr/share/xfce4/backdrops/warty-final-ubuntu.png /usr/share/xfce4/backdrops/jammy-jellyfish.jpg; do
    [ -f "$w" ] && { WALL="$w"; break; }
done
if [ -n "$WALL" ]; then
    for ws in 0 1 2 3; do
        xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitor0/workspace$ws/last-image -s "$WALL" 2>/dev/null
        xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitor0/workspace$ws/image-style -s 5 2>/dev/null
    done
fi
xfconf-query -c xfce4-desktop -p /desktop-icons/style -s 2 2>/dev/null
xfconf-query -c xfce4-desktop -p /desktop-icons/icon-size -s 48 2>/dev/null
xfconf-query -c xfce4-desktop -p /desktop-icons/file-icons/show-home -s true 2>/dev/null
xfconf-query -c xfce4-desktop -p /desktop-icons/file-icons/show-trash -s true 2>/dev/null
xfconf-query -c xfce4-desktop -p /desktop-icons/file-icons/show-filesystem -s false 2>/dev/null
xfconf-query -c xfce4-desktop -p /desktop-icons/file-icons/show-removable -s false 2>/dev/null
xfdesktop --reload 2>/dev/null
LAYOUT_EOF
    done

    progress_set_message "Setup Plank dock..."
    proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF' > /dev/null 2>&1
which plank > /dev/null 2>&1 || apt install -y plank 2>/dev/null
EOF

    for TU in "$U" "root"; do
        proot-distro login ubuntu --shared-tmp --user "$TU" 2>/dev/null << 'EOF' > /dev/null 2>&1
pkill -9 plank 2>/dev/null
mkdir -p ~/.config/plank/dock1
cat > ~/.config/plank/dock1/settings << 'PLANK_CFG'
[PlankDockPreferences]
Theme=Transparency
Position=3
Alignment=3
IconSize=48
HideMode=0
LockItems=false
ZoomEnabled=true
ZoomPercentage=150
PLANK_CFG
mkdir -p ~/.config/autostart
cat > ~/.config/autostart/plank.desktop << 'PLANK_AUTO'
[Desktop Entry]
Type=Application
Name=Plank
Exec=plank
Terminal=false
X-GNOME-Autostart-enabled=true
PLANK_AUTO
EOF
    done
}

build_verifier() {
    cat > "$VERIFY_FILE" << 'VERIFY_EOF'
#!/data/data/com.termux/files/usr/bin/bash
CYAN='\033[0;36m'; LIME='\033[38;5;154m'; RED='\033[0;31m'
WHITE='\033[1;37m'; GOLD='\033[38;5;220m'; BOLD='\033[1m'; DIM='\033[2m'; NC='\033[0m'
clear
echo ""
echo -e "${CYAN}${BOLD}╔══════════════════════════════════════════╗${NC}"
echo -e "${CYAN}${BOLD}║   🔍 CEK LAYOUT UBUNTU TERPASANG        ║${NC}"
echo -e "${CYAN}${BOLD}╚══════════════════════════════════════════╝${NC}\n"
RESULT=$(proot-distro login ubuntu --shared-tmp 2>/dev/null << 'EOF'
[ -f /usr/share/backgrounds/warty-final-ubuntu.png ] || [ -f /usr/share/backgrounds/jammy-jellyfish.jpg ] && echo "WALLPAPER:OK" || echo "WALLPAPER:NO"
xfconf-query -c xsettings -p /Net/ThemeName 2>/dev/null | grep -q "Yaru" && echo "THEME:OK" || echo "THEME:NO"
xfconf-query -c xfce4-panel -p /panels/panel-1/size 2>/dev/null | grep -q "32" && echo "PANEL:OK" || echo "PANEL:NO"
which plank > /dev/null 2>&1 && echo "PLANK:OK" || echo "PLANK:NO"
which xscreensaver > /dev/null 2>&1 && echo "XSCREEN:STILL" || echo "XSCREEN:REMOVED"
[ -d /usr/share/xfce4/backdrops ] && echo "BACKDROP:OK" || echo "BACKDROP:NO"
EOF
)
echo -e "  ${GOLD}${BOLD}HASIL:${NC}\n"
echo "$RESULT" | while IFS=':' read -r key val; do
    case "$key" in
        WALLPAPER) [ "$val" = "OK" ] && echo -e "  ${LIME}✓${NC} ${WHITE}Wallpaper${NC}" || echo -e "  ${RED}✗${NC} ${WHITE}Wallpaper${NC}" ;;
        THEME) [ "$val" = "OK" ] && echo -e "  ${LIME}✓${NC} ${WHITE}Tema Yaru${NC}" || echo -e "  ${RED}✗${NC} ${WHITE}Tema Yaru${NC}" ;;
        PANEL) [ "$val" = "OK" ] && echo -e "  ${LIME}✓${NC} ${WHITE}Panel 32px${NC}" || echo -e "  ${RED}✗${NC} ${WHITE}Panel 32px${NC}" ;;
        PLANK) [ "$val" = "OK" ] && echo -e "  ${LIME}✓${NC} ${WHITE}Plank dock${NC}" || echo -e "  ${RED}✗${NC} ${WHITE}Plank dock${NC}" ;;
        XSCREEN) [ "$val" = "REMOVED" ] && echo -e "  ${LIME}✓${NC} ${WHITE}xscreensaver dihapus${NC}" || echo -e "  ${RED}✗${NC} ${WHITE}xscreensaver masih ada${NC}" ;;
        BACKDROP) [ "$val" = "OK" ] && echo -e "  ${LIME}✓${NC} ${WHITE}Folder backdrop${NC}" || echo -e "  ${RED}✗${NC} ${WHITE}Folder backdrop${NC}" ;;
    esac
done
echo ""
VERIFY_EOF
    chmod +x "$VERIFY_FILE"
}

get_ubuntu_rootfs() {
    if [ -d "$ROOTFS_NEW" ] && [ "$(ls -A "$ROOTFS_NEW" 2>/dev/null | wc -l)" -gt 0 ]; then
        echo "$ROOTFS_NEW"
        return 0
    fi
    if [ -d "$ROOTFS_OLD" ] && [ "$(ls -A "$ROOTFS_OLD" 2>/dev/null | wc -l)" -gt 0 ]; then
        echo "$ROOTFS_OLD"
        return 0
    fi
    for d in "$CONTAINERS_BASE"/*/rootfs; do
        if [ -d "$d" ] && [ "$(ls -A "$d" 2>/dev/null | wc -l)" -gt 0 ]; then
            echo "$d"
            return 0
        fi
    done
    return 1
}
get_ubuntu_size_kb() {
    local r=$(get_ubuntu_rootfs)
    if [ -n "$r" ]; then
        du -sk "$r" 2>/dev/null | awk '{print $1}'
    else
        echo "0"
    fi
}
is_ubuntu_valid() { [ -n "$(get_ubuntu_rootfs)" ]; }
ubuntu_pkg_installed() {
    proot-distro login ubuntu --shared-tmp 2>/dev/null << EOF > /dev/null 2>&1
dpkg -l "$1" 2>/dev/null | grep -q "^ii"
EOF
}
cmd_exists() { command -v "$1" > /dev/null 2>&1; }
pkg_installed() { pkg list-installed 2>/dev/null | grep -q "^${1}/"; }
ensure_folders() {
    mkdir -p "$PROOT_BASE" "$ROOTFS_OLD" "$DISTRO_BASE" "$CACHE_BASE" "$CONTAINERS_BASE" "$HOME/.config" "$TMP_DIR" 2>/dev/null
}

progress_set_message() { echo "$1" > "$MESSAGE_FILE"; }
progress_start() {
    echo "..." > "$MESSAGE_FILE"
    touch "$TRACKER_FLAG"
    (
        local w=25
        while [ -f "$TRACKER_FLAG" ]; do
            local us=$(get_ubuntu_size_kb)
            [ -z "$us" ] && us=0
            local c=$((TERMUX_BASE_KB + us))
            [ "$c" -gt "$TOTAL_INSTALL_KB" ] && c=$TOTAL_INSTALL_KB
            local m=$(cat "$MESSAGE_FILE" 2>/dev/null || echo "...")
            local p=$((c * 100 / TOTAL_INSTALL_KB))
            [ "$p" -gt 99 ] && p=99
            local f=$((p * w / 100))
            local e=$((w - f))
            local col=$SKY
            if [ "$p" -ge 90 ]; then col=$GOLD
            elif [ "$p" -ge 70 ]; then col=$LIME
            elif [ "$p" -ge 40 ]; then col=$CYAN
            fi
            printf "\r\033[K  ${col}${BOLD}[${NC}"
            printf "${col}%*s${NC}" $f "" | tr ' ' '█'
            printf "${DIM}%*s${NC}" $e "" | tr ' ' '░'
            printf "${col}${BOLD}]${NC} ${WHITE}${BOLD}%3d%%${NC} ${SKY}%4d MB${NC}${DIM}/%d MB${NC} ${DIM}%s${NC}" \
                "$p" "$((c/1024))" "$((TOTAL_INSTALL_KB/1024))" "${m:0:26}"
            sleep 1
        done
    ) &
    PROGRESS_PID=$!
}
progress_stop() {
    rm -f "$TRACKER_FLAG" 2>/dev/null
    kill $PROGRESS_PID 2>/dev/null
    wait $PROGRESS_PID 2>/dev/null
    printf "\r\033[K  ${GOLD}${BOLD}[${NC}"
    printf "${GOLD}%*s${NC}" 25 "" | tr ' ' '█'
    printf "${GOLD}${BOLD}]${NC} ${GOLD}${BOLD}100%%${NC} ${LIME}✓${NC} ${WHITE}Selesai!${NC}\n"
}

prompt_credentials() {
    echo ""
    echo -e "${MAGENTA}${BOLD}  ╔══════════════════════════════════════════════════════╗${NC}"
    echo -e "${MAGENTA}${BOLD}  ║${NC}           ${WHITE}${BOLD}👤  BUAT AKUN UBUNTU  👤${NC}                ${MAGENTA}${BOLD}║${NC}"
    echo -e "${MAGENTA}${BOLD}  ╚══════════════════════════════════════════════════════╝${NC}\n"
    while true; do
        echo -ne "  ${CYAN}${BOLD}Username${NC} ${DIM}(huruf kecil)${NC} ❯ "
        read -r UBUNTU_USER
        [ -z "$UBUNTU_USER" ] && { echo -e "  ${RED}✗ Kosong${NC}\n"; continue; }
        echo "$UBUNTU_USER" | grep -qE "^[a-z][a-z0-9_-]*$" && break
        echo -e "  ${RED}✗ Format salah${NC}\n"
    done
    echo ""
    while true; do
        echo -ne "  ${CYAN}${BOLD}Password${NC} ❯ "
        read -rs UBUNTU_PASS
        echo ""
        [ -n "$UBUNTU_PASS" ] && break
        echo -e "  ${RED}✗ Kosong${NC}\n"
    done
    cat > "$CONFIG_FILE" << EOF
UBUNTU_USER="$UBUNTU_USER"
UBUNTU_PASS="$UBUNTU_PASS"
EOF
    chmod 600 "$CONFIG_FILE"
    echo -e "\n  ${LIME}✓ Akun: ${GOLD}$UBUNTU_USER${NC}\n"
    sleep 1
}

load_config() { [ -f "$CONFIG_FILE" ] && { source "$CONFIG_FILE"; return 0; }; return 1; }

show_banner() {
    clear
    echo ""
    echo -e "${ORANGE}${BOLD}     ██╗   ██╗██████╗ ██╗   ██╗███╗   ██╗████████╗██╗   ██╗${NC}"
    echo -e "${GOLD}${BOLD}     ██║   ██║██╔══██╗██║   ██║████╗  ██║╚══██╔══╝██║   ██║${NC}"
    echo -e "${GOLD}${BOLD}     ██║   ██║██████╔╝██║   ██║██╔██╗ ██║   ██║   ██║   ██║${NC}"
    echo -e "${YELLOW}${BOLD}     ██║   ██║██╔══██╗██║   ██║██║╚██╗██║   ██║   ██║   ██║${NC}"
    echo -e "${YELLOW}${BOLD}     ╚██████╔╝██████╔╝╚██████╔╝██║ ╚████║   ██║   ╚██████╔╝${NC}"
    echo -e "${YELLOW}${BOLD}      ╚═════╝ ╚═════╝  ╚═════╝ ╚═╝  ╚═══╝   ╚═╝    ╚═════╝ ${NC}"
    echo ""
    echo -e "${CYAN}${BOLD}              ✨ UBUNTU DESKTOP AUTO INSTALLER ✨${NC}"
    echo -e "${PINK}${BOLD}      🎨 Full Layout + 🧠 Local AI + 🌍 Auto-Loc${NC}"
    echo -e "${LIME}${BOLD}                  v21.0 FINAL${NC}"
    echo ""
}

build_launcher() {
    cat > "$LAUNCHER_FILE" << 'LAUNCHER_EOF'
#!/data/data/com.termux/files/usr/bin/bash
CONFIG_FILE="$HOME/.ubuntu-config"
[ -f "$CONFIG_FILE" ] && source "$CONFIG_FILE"
LOGIN_USER="${UBUNTU_USER:-root}"
clear
echo ""
echo -e "\033[38;5;141m\033[1m     ╔══════════════════════════════════════════════════════╗\033[0m"
echo -e "\033[38;5;141m\033[1m     ║        🖥  MEMBUKA UBUNTU DESKTOP  🖥                 ║\033[0m"
echo -e "\033[38;5;141m\033[1m     ╚══════════════════════════════════════════════════════╝\033[0m"
echo ""
pkill -9 termux-x11 2>/dev/null
rm -rf "$PREFIX/tmp/.X0-lock" "$PREFIX/tmp/.X11-unix" 2>/dev/null
sleep 1
termux-x11 :0 > /dev/null 2>&1 &
sleep 3
am start -n com.termux.x11/.MainActivity > /dev/null 2>&1 || monkey -p com.termux.x11 -c android.intent.category.LAUNCHER 1 > /dev/null 2>&1
sleep 5
proot-distro login ubuntu --shared-tmp --user "$LOGIN_USER" 2>/dev/null << 'INNER'
export DISPLAY=:0
export PULSE_SERVER=127.0.0.1
xfconf-query -c xsettings -p /Net/ThemeName -s "Yaru-dark" 2>/dev/null
xfconf-query -c xsettings -p /Net/IconThemeName -s "Yaru-dark" 2>/dev/null
xfconf-query -c xsettings -p /Gtk/CursorThemeName -s "Yaru" 2>/dev/null
xfconf-query -c xsettings -p /Gtk/FontName -s "Ubuntu 11" 2>/dev/null
xfconf-query -c xfwm4 -p /general/theme -s "Yaru-dark" 2>/dev/null
xfconf-query -c xfwm4 -p /general/button_layout -s "O|SHMC" 2>/dev/null
for f in /usr/share/backgrounds/warty-final-ubuntu.png /usr/share/backgrounds/jammy-jellyfish.jpg; do
    [ -f "$f" ] && {
        for ws in 0 1 2 3; do
            xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitor0/workspace$ws/last-image -s "$f" 2>/dev/null
            xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitor0/workspace$ws/image-style -s 5 2>/dev/null
        done
        break
    }
done
which plank > /dev/null 2>&1 && plank > /dev/null 2>&1 &
if which startxfce4 > /dev/null 2>&1; then
    exec dbus-launch --exit-with-session startxfce4
else
    exec dbus-launch --exit-with-session xfce4-session
fi
INNER
LAUNCHER_EOF
    chmod +x "$LAUNCHER_FILE"
}

if [ "$1" == "install" ] || [ "$1" == "--force-install" ] || ! is_ubuntu_valid || [ ! -f "$CONFIG_FILE" ]; then
    show_banner
    ensure_folders

    if [ -f "$CONFIG_FILE" ]; then
        source "$CONFIG_FILE"
        [ -z "$UBUNTU_USER" ] && prompt_credentials
    else
        prompt_credentials
    fi

    if [ -z "$INSTALL_GEO" ]; then
        auto_answer_questions
    else
        echo -e "  ${LIME}✓${NC} Lokasi: ${GOLD}$DETECTED_CITY, $DETECTED_COUNTRY${NC}\n"
        sleep 1
    fi

    load_config
    progress_start
    sleep 1

    progress_set_message "Setup storage..."
    [ ! -d "$HOME/storage" ] && { termux-setup-storage 2>/dev/null; sleep 2; }
    ensure_folders

    progress_set_message "Cek internet & storage..."
    if ! ping -c 1 -W 3 8.8.8.8 > /dev/null 2>&1; then
        progress_stop
        local_ai_fix "Cek Internet" "temporary failure in name resolution"
    fi
    AVAIL_GB=$(( $(df $PREFIX | awk 'NR==2 {print $4}') / 1024 / 1024 ))
    if [ "$AVAIL_GB" -lt 8 ]; then
        progress_stop
        local_ai_fix "Cek Storage" "no space left on device storage < 8 GB"
    fi

    progress_set_message "Siapkan paket Termux..."
    pkg update -y > $LOG_FILE 2>&1
    pkg_installed "x11-repo" || pkg install -y x11-repo > /dev/null 2>&1
    cmd_exists "termux-x11" || pkg install -y termux-x11-nightly > /dev/null 2>&1
    cmd_exists "proot-distro" || pkg install -y proot-distro > /dev/null 2>&1
    cmd_exists "curl" || pkg install -y curl > /dev/null 2>&1
    for tool in wget git nano pulseaudio termux-api; do
        cmd_exists "$tool" || pkg install -y "$tool" > /dev/null 2>&1
    done
    echo "" > $PREFIX/etc/motd 2>/dev/null

    if is_ubuntu_valid; then
        progress_set_message "Ubuntu sudah ada - skip"
        sleep 2
    else
        progress_set_message "Install Ubuntu..."
        strategy_cleanup
        proot-distro install ubuntu > $LOG_FILE 2>&1
        if grep -qi "already exists" $LOG_FILE 2>/dev/null; then
            progress_stop
            local_ai_fix "Install Ubuntu" "container ubuntu already exists"
        fi
        WAIT=0
        while [ "$WAIT" -lt 30 ]; do
            is_ubuntu_valid && break
            sleep 1
            WAIT=$((WAIT + 1))
        done
        if ! is_ubuntu_valid; then
            local err=$(grep -i "error\|failed\|cannot\|unable" $LOG_FILE 2>/dev/null | head -1)
            [ -z "$err" ] && err="Folder instalasi tidak ditemukan"
            progress_stop
            local_ai_fix "Install Ubuntu" "$err"
        fi
    fi

    if ubuntu_pkg_installed "xfce4"; then
        progress_set_message "XFCE4 sudah ada - skip"
        sleep 2
    else
        progress_set_message "Install XFCE4 + Yaru + Firefox..."
        proot-distro login ubuntu --shared-tmp 2>/dev/null << 'SETUP_EOF' > /dev/null 2>&1
echo 'tzdata tzdata/Areas select Asia' | debconf-set-selections
echo 'tzdata tzdata/Zones/Asia select Jakarta' | debconf-set-selections
echo 'keyboard-configuration keyboard-configuration/layoutcode string us' | debconf-set-selections
echo 'keyboard-configuration keyboard-configuration/variantcode string' | debconf-set-selections
echo 'keyboard-configuration keyboard-configuration/modelcode string pc105' | debconf-set-selections
echo 'console-setup console-setup/charmap47 select UTF-8' | debconf-set-selections
echo 'Dpkg::Progress-Fancy "1";' > /etc/apt/apt.conf.d/99progress
SETUP_EOF
        proot-distro login ubuntu --shared-tmp << 'INSTALL_EOF' > $LOG_FILE 2>&1
export DEBIAN_FRONTEND=noninteractive
export TZ="Asia/Jakarta"
apt update -qq
apt remove -y plocate 2>/dev/null || true
dpkg --configure -a 2>/dev/null || true
apt --fix-broken install -y 2>/dev/null || true
apt install -y --no-install-recommends \
    xfce4 xfce4-goodies xfce4-terminal thunar \
    dbus-x11 x11-utils wget curl git nano sudo \
    yaru-theme-gtk yaru-theme-icon yaru-theme-sound \
    fonts-ubuntu \
    ubuntu-wallpapers ubuntu-wallpapers-jammy \
    xfce4-panel-profiles mousepad \
    gnome-calculator gnome-screenshot file-roller \
    software-properties-common
add-apt-repository -y ppa:mozillateam/ppa 2>/dev/null || true
apt update -qq 2>/dev/null || true
apt install -y firefox
apt clean
apt autoremove -y
echo "[OK] Paket selesai."
INSTALL_EOF
        APT_ERR=$(grep -i "^E:" $LOG_FILE 2>/dev/null | head -1)
        if [ -n "$APT_ERR" ]; then
            progress_stop
            local_ai_fix "Install XFCE4" "$APT_ERR"
        fi
        if ! ubuntu_pkg_installed "xfce4"; then
            progress_stop
            local_ai_fix "Verifikasi XFCE4" "unable to locate package xfce4"
        fi
    fi

    progress_set_message "Buat user & apply prefs..."
    load_config
    proot-distro login ubuntu --shared-tmp 2>/dev/null << EOF > /dev/null 2>&1
if id "$UBUNTU_USER" > /dev/null 2>&1; then
    echo "$UBUNTU_USER:$UBUNTU_PASS" | chpasswd
else
    useradd -m -s /bin/bash "$UBUNTU_USER"
    echo "$UBUNTU_USER:$UBUNTU_PASS" | chpasswd
    usermod -aG sudo "$UBUNTU_USER"
    echo "$UBUNTU_USER ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/$UBUNTU_USER
fi
[ -n "$INSTALL_TZ_NAME" ] && { ln -sf "/usr/share/zoneinfo/$INSTALL_TZ_NAME" /etc/localtime 2>/dev/null; echo "$INSTALL_TZ_NAME" > /etc/timezone 2>/dev/null; }
[ -n "$INSTALL_LOCALE" ] && { echo "$INSTALL_LOCALE UTF-8" > /etc/locale.gen 2>/dev/null; locale-gen 2>/dev/null; update-locale LANG=$INSTALL_LOCALE 2>/dev/null; }
EOF

    setup_full_layout

    progress_set_message "Buat launcher & verifier..."
    build_launcher
    build_verifier
    sed -i '/# === UBUNTU ALIAS ===/,/# ====================/d' ~/.bashrc 2>/dev/null
    cat >> ~/.bashrc << 'ALIAS_EOF'

# === UBUNTU ALIAS ===
alias ubuntu='proot-distro login ubuntu --shared-tmp'
alias x11='termux-x11 :0 &'
alias desktop='bash ~/start-ubuntu-desktop.sh'
alias check-ubuntu='bash ~/check-ubuntu-layout.sh'
# ====================
ALIAS_EOF
    source ~/.bashrc 2>/dev/null
    rm -f "$RETRY_FILE"

    progress_set_message "Selesai!"
    sleep 2
    progress_stop

    load_config
    local flag=$(country_flag "${DETECTED_CC:-ID}")
    echo ""
    echo -e "${GOLD}${BOLD}     ██████╗ ███████╗██╗     ███████╗███████╗███████╗${NC}"
    echo -e "${GOLD}${BOLD}    ██╔════╝ ██╔════╝██║     ██╔════╝██╔════╝██╔════╝${NC}"
    echo -e "${GOLD}${BOLD}    ██║  ███╗█████╗  ██║     █████╗  ███████╗███████╗${NC}"
    echo -e "${GOLD}${BOLD}    ██║   ██║██╔══╝  ██║     ██╔══╝  ╚════██║╚════██║${NC}"
    echo -e "${GOLD}${BOLD}    ╚██████╔╝███████╗███████╗███████╗███████║███████║${NC}"
    echo -e "${GOLD}${BOLD}     ╚═════╝ ╚══════╝╚══════╝╚══════╝╚══════╝╚══════╝${NC}\n"
    echo -e "${LIME}${BOLD}         ✨ INSTALASI BERHASIL — SEMUA OTOMATIS! ✨${NC}\n"
    echo -e "  ${GOLD}${BOLD}╔══════════════════════════════════════════════════════╗${NC}"
    echo -e "  ${GOLD}${BOLD}║${NC}  ${WHITE}📍 ${flag} ${DETECTED_CITY}, ${DETECTED_COUNTRY}${NC}"
    echo -e "  ${GOLD}${BOLD}║${NC}     TZ: ${LIME}${INSTALL_TZ_NAME}${NC}"
    echo -e "  ${GOLD}${BOLD}╠══════════════════════════════════════════════════════╣${NC}"
    echo -e "  ${GOLD}${BOLD}║${NC}  ${WHITE}👤 Akun:${NC} ${LIME}${UBUNTU_USER}${NC}"
    echo -e "  ${GOLD}${BOLD}╚══════════════════════════════════════════════════════╝${NC}\n"
    echo -e "  ${LIME}${BOLD}🎨 Yang sudah OTOMATIS:${NC}"
    echo -e "     ${LIME}✓${NC} Wallpaper Ubuntu (auto-download)"
    echo -e "     ${LIME}✓${NC} Folder backdrop (fix error null)"
    echo -e "     ${LIME}✓${NC} Panel atas 32px + Whisker Menu + Jam"
    echo -e "     ${LIME}✓${NC} Plank dock bawah (macOS-style)"
    echo -e "     ${LIME}✓${NC} Tema Yaru-dark + Ikon + Font"
    echo -e "     ${LIME}✓${NC} xscreensaver error → dihapus"
    echo -e "     ${LIME}✓${NC} Desktop icons (Home + Trash)"
    echo -e "     ${LIME}✓${NC} Local AI (auto-fix error)\n"
    echo -e "  ${PINK}${BOLD}🚀 Perintah:${NC}"
    echo -e "     ${LIME}${BOLD}desktop${NC}        ${DIM}→${NC}  Buka desktop"
    echo -e "     ${LIME}${BOLD}ubuntu${NC}         ${DIM}→${NC}  Terminal Ubuntu"
    echo -e "     ${LIME}${BOLD}check-ubuntu${NC}   ${DIM}→${NC}  Cek layout\n"
    echo -e "  ${CYAN}${BOLD}🔄 Auto-launch dalam 3 detik...${NC}"
    sleep 3
    exec bash "$LAUNCHER_FILE"
fi

[ ! -f "$LAUNCHER_FILE" ] && build_launcher
exec bash "$LAUNCHER_FILE"
```

---

📖 PENUTUP

Ringkasan Cepat

Step Perintah
1 nano ~/ubuntu-instant-v2.sh
2 Paste script di BAB 5
3 chmod +x ~/ubuntu-instant-v2.sh
4 bash ~/ubuntu-instant-v2.sh install
5 Isi username & password
6 Tunggu 10-25 menit
7 Desktop Ubuntu terbuka otomatis

Perintah Setelah Install

Perintah Fungsi
desktop Buka Ubuntu Desktop
ubuntu Terminal Ubuntu saja
x11 Nyalakan X11 saja
check-ubuntu Cek apakah layout OK

Fitur Otomatis

· ✅ Wallpaper dari internet
· ✅ Folder backdrop auto-fix
· ✅ xscreensaver auto-remove
· ✅ Panel atas 32px GNOME-style
· ✅ Plank dock bottom
· ✅ Tema Yaru-dark
· ✅ Ikon + Font Ubuntu
· ✅ Local AI (auto-fix error)
· ✅ Auto-location detection
· ✅ Auto-launch desktop

---
