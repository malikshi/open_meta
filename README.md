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

Setelah mengedit config main.yaml dan setiap file pada folder proxy_provider serta rule_direct.yaml pada folder rule_provider maka kita akan setting openclash via luCI. Silahkan Login LuCI dan masuk ke Services > Openclash

## Global Setting

Hasil settingan pada global setting akan meng-overide settingal awal pada file main.yaml.

### Operation Mode

- Operation Mode **SWITCH PAGE TO FAKE IP MODE** terlebih dahulu.
- Ceklist/centang opsi sesuai gambar berikut:

<img src="https://raw.githubusercontent.com/malikshi/open_meta/main/Assets/operationmode.jpg" border="0">

### DNS Setting

- Ceklist/Centang sesuai gambar:

<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/dnssetting.jpg" border="0">

- Isi Fallback-filter

Perlu diedit isi fallback-filternya supaya mendapatkan hostname di Yacd Connection log. isi fallback-filter dengan ini.

```yaml
fallback-filter:
  geoip: true
  geoip-code: ID
  ipcidr:
    - 0.0.0.0/8
    - 10.0.0.0/8
    - 100.64.0.0/10
    - 127.0.0.0/8
    - 169.254.0.0/16
    - 172.16.0.0/12
    - 192.0.0.0/24
    - 192.0.2.0/24
    - 192.88.99.0/24
    - 192.168.0.0/16
    - 198.18.0.0/15
    - 198.51.100.0/24
    - 203.0.113.0/24
    - 224.0.0.0/4
    - 240.0.0.0/4
    - 255.255.255.255/32
  domain:
    - "+.google.com"
    - "+.facebook.com"
    - "+.youtube.com"
    - "+.githubusercontent.com"
    - "+.googlevideo.com"
    - "+.msftconnecttest.com"
    - "+.msftncsi.com"
    - msftconnecttest.com
    - msftncsi.com
    - "+.*"
```

- Tambahkan Server Group name server dan fallback masing masing 2 seperti pada gambar berikut.

<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/dns-fallback.jpg" border="0">

DNS Server Group | DNS Server Address | DNS Server Port | DNS Server Type
------------ | ------------- | ------------- | -------------
NameServer | dns.quad9.net/dns-query |   | HTTPS
NameServer | 9.9.9.9 | 853 | TLS
FallBack | dns.quad9.net/dns-query |   | HTTPS
FallBack | 149.112.112.112 | 853 | TLS

### GEOIP Update

Pada rule_indo.yaml menggunakan geoip:ID dimana jika IP tersebut bercode/berasal negara Indonesia maka akan menggunakan trafficIndo.yaml dan itu membutuhkan mmdb yang selalu updated sebagai data geoip seluruh negara.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/geoip-update.jpg" border="0">

## Manage Config

Mulai dari versi v0.44.22-beta pada branch dev, menu Manage Config support dengan fungsi create,edit,delete file jadi tidak perlu login ssh untuk edit via terminal router openwrt. Tidak membutuhkan tiny fm (file manager) karena config editor built-in openclash terdapat validator config jika terdapat kesalahan/error saat melakukan pengeditan.

### Import Main.yaml

Setelah melakukan pengeditan main.yaml maka kita import main.yaml via Manage Config. Dan khusus main.yaml jangan import/edit melalui winscp/sftp.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/main-upload.jpg" border="0">

### Import Proxy Provider

Jika Semua file pada folder proxy_provider yang terdiri dari vvip-id.yaml, vvip-sg.yaml, vvip-game.yaml yang sudah diisi dengan akun maka selanjutnya import file-file tersebut pada **Upload File Type : Proxy Provider File**.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/proxy-upload.jpg" border="0">

### Import Rule Provider

traffic direct/bypass sudah disikan ke rule_direct.yaml maka bisa langsung import semua files pada folder rule_provider pada **Upload File Type : Rule Provider File**.
<img src="https://raw.githubusercontent.com/malikshi/open_clash/main/assets/rule-upload.jpg" border="0">
