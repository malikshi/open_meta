**Table of Contents**
- [OpenClash Meta Kernel](#openclash-meta-kernel)


# OpenClash Meta Kernel

OpenClash Config untuk VVIP IPTUNNELS

- [Buy VVIP IPTUNNELS](https://linktr.ee/iptunnelscom)
- [Join Telegram](https://t.me/joinchat/RihiceTtK1QhBMm7)
- [Requests Rules](https://github.com/malikshi/open_clash/issues/new/choose)

# Features

- Support Multi-WAN/Modem
- Menggunakan Custom Geosite!
- Support Pisah Traffic!
- Support GEOSITE Adblock, Privacy & P0rn.
- Support GEOSITE GAME
- Support Filtering Port Games
- Support GEOSITE INDO
- Support GEOSITE STREAMING
- Support GEOSITE SOSMED
- Support Direct/Bypass traffik.

# Setting Openclash App

Setelah mengedit config iptunnels.yaml dan setiap file pada folder proxy_provider serta rule_direct.yaml pada folder rule_provider maka kita akan setting openclash via luCI. Silahkan Login LuCI dan masuk ke Services > Openclash

# Global Setting

Hasil settingan pada global setting akan meng-overide settingal awal pada file iptunnels.yaml.

## Operation Mode

- Operation Mode **SWITCH PAGE TO FAKE IP MODE** terlebih dahulu.
- Ceklist/centang opsi sesuai gambar berikut:

<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/images/operationmode.jpg" border="0">

## DNS Setting

- Ceklist/Centang sesuai gambar:

<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/images/dnssetting-1.jpg" border="0">

- Tambahkan Server Group name server dan fallback masing masing 2 seperti pada gambar berikut.

<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/dns-fallback.jpg" border="0">

DNS Server Group | DNS Server Address | DNS Server Port | DNS Server Type
------------ | ------------- | ------------- | -------------
NameServer | dns.quad9.net/dns-query |   | HTTPS
NameServer | 9.9.9.9 | 853 | TLS
FallBack | dns.quad9.net/dns-query |   | HTTPS
FallBack | 149.112.112.112 | 853 | TLS

## Meta Setting


Disini akan menggunakan Meta kernel jadi harus mengatur meta setting.
<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/images/metasetting-1.jpg" border="0">

<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/images/metasetting-2.jpg" border="0">

### GEOIP

Wajib menggunakan GeoIP.dat silahkan setting sesuai gambar
<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/images/metasetting-3.jpg" border="0">

Jika belum ada GeoIP pada folder `/etc/openclash/` maka silahkan download terlebih dahulu.

```sh
wget -O /etc/openclash/GeoIP.dat https://raw.githubusercontent.com/malikshi/v2ray-rules-dat/release/geoip.dat
chmod 744 /etc/openclash/GeoIP.dat
```

### GEOSITE

Karena semua rule kami pindahkan ke GeoSite.dat maka perlu setting `custom geosite url` menggunakan hasil compile custom list yang telah kami sediakan.

```sh
https://raw.githubusercontent.com/malikshi/v2ray-rules-dat/release/geosite.dat
```
Perhatikan gambar berikut.

<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/images/metasetting-4.jpg" border="0">

WAJIB menggunakan GeoSite custom kami. Silahkan download terlebih dahulu.

```sh
wget -O /etc/openclash/GeoSite.dat https://raw.githubusercontent.com/malikshi/v2ray-rules-dat/release/geosite.dat
chmod 744 /etc/openclash/GeoSite.dat
```

# Setting Config

Untuk pengaturan config dan proxy_provider silahkan cek repo kami
- [Cara mengisi akun](https://github.com/malikshi/open_clash#cara-mengisi-akun)
- [Edit Proxy Provider](https://github.com/malikshi/open_clash#edit-files-proxy-provider)

## Import iptunnels.yaml

Setelah melakukan pengeditan iptunnels.yaml maka kita import iptunnels.yaml via Manage Config. Dan khusus iptunnels.yaml jangan import/edit melalui winscp/sftp.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/main-upload.jpg" border="0">

## Import Proxy Provider

Jika Semua file pada folder proxy_provider yang terdiri dari vvip-id.yaml, vvip-sg.yaml, vvip-game.yaml yang sudah diisi dengan akun maka selanjutnya import file-file tersebut pada **Upload File Type : Proxy Provider File**.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/proxy-upload.jpg" border="0">

## Import Rule Provider

traffic direct/bypass sudah disikan ke rule_direct.yaml maka bisa langsung import semua files pada folder rule_provider pada **Upload File Type : Rule Provider File**.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/rule-upload.jpg" border="0">

# Test Adblock 100%

Silahkan test rules adblock melalui [https://d3ward.github.io/toolz/adblock.html](https://d3ward.github.io/toolz/adblock.html)

Hasil test:
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/d3ward.jpg" border="0">