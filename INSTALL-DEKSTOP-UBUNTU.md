# 📚 Panduan Ubuntu Proot-Distro di Termux

## 🏁 Langkah Pertama

### 1. Install Paket Wajib di Termux

Buka aplikasi Termux dan jalankan perintah berikut:

```bash
pkg update
```

Tunggu update selesai, kemudian install repository dan paket yang diperlukan:

```bash
pkg install x11-repo
```

Install semua paket dependencies:

```bash
pkg install termux-x11-nightly pulseaudio proot-distro wget
```

### 2. Install Ubuntu Proot-Distro

Jalankan perintah untuk install Ubuntu:

```bash
proot-distro install ubuntu
```

Tunggu proses instalasi selesai (bisa memakan waktu beberapa menit tergantung kecepatan internet).

### 3. Login ke Lingkungan Ubuntu

Setelah instalasi selesai, login ke Ubuntu:

```bash
proot-distro login ubuntu
```

Anda sekarang berada di dalam lingkungan Ubuntu.

### 4. Update Repository Ubuntu

Di dalam Ubuntu, jalankan:

```bash
apt update
```

Tunggu hingga selesai, kemudian upgrade:

```bash
apt upgrade
```

### 5. Install Paket Dasar

Install sudo dan text editor vim:

```bash
apt install sudo vim -y
```

---

## ⬇️ Unduh Skrip Peluncur Desktop

### Download Script untuk XFCE4

Jalankan perintah ini di dalam Ubuntu:

```bash
wget https://raw.githubusercontent.com/LinuxDroidMaster/Termux-Desktops/main/scripts/proot_ubuntu/startxfce4_ubuntu.sh
```

Ubah permission agar bisa dijalankan:

```bash
chmod +x startxfce4_ubuntu.sh
```

### Download Script untuk KDE Plasma

Jalankan perintah ini di dalam Ubuntu:

```bash
wget https://raw.githubusercontent.com/LinuxDroidMaster/Termux-Desktops/main/scripts/proot_ubuntu/startplasma_ubuntu.sh
```

Ubah permission agar bisa dijalankan:

```bash
chmod +x startplasma_ubuntu.sh
```

---

## ⚙️ Instalasi Desktop Environment

### Langkah 1: Hapus PPA Mozilla (Opsional)

Install utility ppa-purge:

```bash
sudo apt install ppa-purge -y
```

Hapus Mozilla PPA jika ada:

```bash
sudo ppa-purge ppa:mozillateam/ppa
```

Hapus ppa-purge setelah selesai:

```bash
sudo apt autopurge ppa-purge -y
```

### Langkah 2: Buat User Baru

Buat user baru untuk menjalankan desktop:

```bash
sudo adduser droidmaster
```

Sistem akan meminta password, masukkan password pilihan Anda (bisa Enter untuk melewati fields lainnya).

Pindah ke user baru:

```bash
su - droidmaster
```

Masukkan password yang baru saja dibuat.

### Langkah 3: Disable Snapd

Buat file konfigurasi untuk menonaktifkan snap:

```bash
cat <<EOF | sudo tee /etc/apt/preferences.d/nosnap.pref
# Untuk mencegah instalasi snap, file ini melarang snapd
# untuk diinstall melalui APT
Package: snapd
Pin: release a=*
Pin-Priority: -10
EOF
```

### Langkah 4: Instalasi Desktop Environment

#### Pilihan A: XFCE4 (Ringan & Cepat - Rekomendasi)

```bash
sudo apt install xubuntu-desktop -y
```

Tunggu hingga instalasi selesai.

#### Pilihan B: KDE Plasma (Berat tapi Powerful)

```bash
sudo apt install kubuntu-desktop -y
```

Tunggu hingga instalasi selesai.

#### Pilihan C: Cinnamon (Sedang)

```bash
sudo apt install ubuntucinnamon-desktop -y
```

Tunggu hingga instalasi selesai.

---

## 🦊 Instalasi Firefox

### Langkah 1: Import Kunci Signing Mozilla

Unduh dan import kunci signing Mozilla:

```bash
wget -q https://packages.mozilla.org/apt/repo-signing-key.gpg -O- | sudo tee /etc/apt/keyrings/packages.mozilla.org.asc > /dev/null
```

### Langkah 2: Tambahkan Repository Mozilla

Tambahkan sumber repository resmi Mozilla:

```bash
cat <<EOF | sudo tee /etc/apt/sources.list.d/mozilla.sources
Types: deb
URIs: https://packages.mozilla.org/apt
Suites: mozilla
Components: main
Signed-By: /etc/apt/keyrings/packages.mozilla.org.asc
EOF
```

### Langkah 3: Prioritas Repository Mozilla

Atur prioritas APT untuk repository Mozilla:

```bash
echo '
Package: *
Pin: origin packages.mozilla.org
Pin-Priority: 1000
' | sudo tee /etc/apt/preferences.d/mozilla
```

### Langkah 4: Update dan Install Firefox

Update repository:

```bash
sudo apt update
```

Install Firefox versi terbaru:

```bash
sudo apt install firefox -y
```

Tunggu hingga instalasi selesai.

---

## ▶️ Menjalankan Desktop

### Jalankan X11 Server

Buka terminal Termux (tab baru) dan jalankan:

```bash
termux-x11 :0
```

### Login ke Ubuntu

Di terminal Termux yang lain, login ke Ubuntu:

```bash
proot-distro login ubuntu
```

Masuk sebagai user droidmaster:

```bash
su - droidmaster
```

### Jalankan Desktop Environment

#### Untuk XFCE4:

```bash
./startxfce4_ubuntu.sh
```

#### Untuk KDE Plasma:

```bash
./startplasma_ubuntu.sh
```

Desktop akan muncul di aplikasi Termux X11.

---

## 📝 Catatan Penting

- **Proses instalasi pertama kali** memerlukan koneksi internet yang stabil dan bisa memakan waktu 15-30 menit
- **Simpan password** yang Anda buat untuk user droidmaster agar dapat login di kemudian hari
- **XFCE4 paling ringan** untuk perangkat dengan RAM terbatas
- **KDE Plasma paling lengkap** tapi memerlukan spesifikasi yang lebih tinggi
- **Jangan gunakan perintah sudo** untuk task yang tidak perlu karena bisa memperlambat sistem

---

## 🐛 Troubleshooting

### Error Saat Install Paket

Jika mendapat error, coba:

```bash
sudo apt clean
sudo apt autoclean
sudo apt autoremove
sudo apt update
```

### X11 Tidak Muncul

Pastikan aplikasi Termux X11 sudah diinstall dari Play Store dan dijalankan sebelum menjalankan desktop.

### Slow Performance

Reduce aplikasi yang berjalan di background atau pilih XFCE4 alih-alih KDE Plasma.

---

## ✅ Verifikasi Instalasi

Untuk memastikan semua terinstall dengan benar:

```bash
# Cek versi Ubuntu
lsb_release -a

# Cek Firefox
firefox --version

# Cek desktop environment (XFCE)
xfce4-about

# Cek desktop environment (KDE)
plasmashell --version
```

---

## 📞 Butuh Bantuan?

Referensi lengkap:
- [Video Tutorial (Outdated)](https://www.youtube.com/watch?v=_vxhzSG2zVQ)
- [Blog Ivon (English)](https://ivonblog.com/en-us/posts/termux-proot-distro-ubuntu/)
- [Dokumentasi Mozilla Firefox](https://support.mozilla.org/en-US/kb/install-firefox-linux)
