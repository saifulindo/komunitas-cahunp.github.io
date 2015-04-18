---
layout: post

title: Mengatasi kesalahan saat konfigurasi DNS Server
subtitle: "Domain Name System"
cover_image: 

excerpt: "DNS Server adalah metode untuk mengkonversikan IP Address suatu komputer ke dalam suatu nama domain, ataupun sebaliknya."

author:
  name: Rusit Affandy
  twitter: 
  bio: http://read-me.tk/sample-page/
  image: 
---

Ditengah kesibukan mengerjakan tugas akhir dan ada beberapa kesibukan lainya saya sempetin nulis di komunitas tercinta ini. Langsung saja temen2, kali ini saya akan posting bagaimana mengatasi kesalahan saat temen2 mencoba Konfigurasi DNS Server dengan Bind. DNS Server adalah metode untuk mengkonversikan IP Address suatu komputer ke dalam suatu nama domain, ataupun sebaliknya. Dengan adanya DNS Server dapat memudahkan kita untuk mengakses IP suatu komputer/website dengan mengetikan nama domain bukan lagi IP Address. Misal saya punya komputer dengan IP Address 192.168.56.10 dengan adanya dns kalian tinggal ketik di browser misal (rocksyd.net).

Nah ketika saya mencoba menginstall DNS Server dan mengkonfigurasinya. Saya mendapatkan kendala saat restart Bind seperti yang terlihat pada gambar berikut.
<div class="full zoomable"><img src="/images/kendala-restart-bind.png"></div>
untuk melihat kesalahan saat restart bind tersebut, coba ketikkan pada terminal sobat seperti ini.
<div class="full zoomable"><img src="/images/named-g-p-53.png"></div>
oke. Dari keterangan log tersebut terlihat bahwa kesalahan ada file `/etc/bind/named.conf` yaitu pada `;` sebelum `zone`. Lalu coba cek pada `/etc/bind/named.conf` dengan editor file kesangan anda. Misal :
`root@snort-ids:~# nano /etc/bind/named.conf`

Kalau sudah, coba sobat restart bind
`root@snort-ids:~# service bind9 restart`

lalu lihat hasilnya.
