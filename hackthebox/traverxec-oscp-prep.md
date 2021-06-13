# TRAVERXEC / OSCP PREP

![](../.gitbook/assets/c51addd6daed4142849d20b8c0f6c648.png)

## NMAP SCAN

```text
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 63 OpenSSH 7.9p1 Debian 10+deb10u1 (protocol 2.0)
| ssh-hostkey: 
|   2048 aa:99:a8:16:68:cd:41:cc:f9:6c:84:01:c7:59:09:5c (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDVWo6eEhBKO19Owd6sVIAFVCJjQqSL4g16oI/DoFwUo+ubJyyIeTRagQNE91YdCrENXF2qBs2yFj2fqfRZy9iqGB09VOZt6i8oalpbmFwkBDtCdHoIAZbaZFKAl+m1UBell2v0xUhAy37Wl9BjoUU3EQBVF5QJNQqvb/mSqHsi5TAJcMtCpWKA4So3pwZcTatSu5x/RYdKzzo9fWSS6hjO4/hdJ4BM6eyKQxa29vl/ea1PvcHPY5EDTRX5RtraV9HAT7w2zIZH5W6i3BQvMGEckrrvVTZ6Ge3Gjx00ORLBdoVyqQeXQzIJ/vuDuJOH2G6E/AHDsw3n5yFNMKeCvNNL
|   256 93:dd:1a:23:ee:d7:1f:08:6b:58:47:09:73:a3:88:cc (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBLpsS/IDFr0gxOgk9GkAT0G4vhnRdtvoL8iem2q8yoRCatUIib1nkp5ViHvLEgL6e3AnzUJGFLI3TFz+CInilq4=
|   256 9d:d6:62:1e:7a:fb:8f:56:92:e6:37:f1:10:db:9b:ce (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGJ16OMR0bxc/4SAEl1yiyEUxC3i/dFH7ftnCU7+P+3s
80/tcp open  http    syn-ack ttl 63 nostromo 1.9.6
|_http-favicon: Unknown favicon MD5: FED84E16B6CCFE88EE7FFAAE5DFEFD34
| http-methods: 
|_  Supported Methods: GET HEAD POST
|_http-server-header: nostromo 1.9.6
|_http-title: TRAVERXEC
```

## PORT 80

### GOBUSTER

```text
/Readme.txt (Status: 200) [Size: 203]
/empty.html (Status: 200) [Size: 55]
/icons (Status: 301) [Size: 314]
/img (Status: 301) [Size: 314]
/index.html (Status: 200) [Size: 15674]
/index.html (Status: 200) [Size: 15674]
```

### NOSTROMO

* [https://www.exploit-db.com/exploits/47837](https://www.exploit-db.com/exploits/47837)

![](../.gitbook/assets/c814eaee2d1548dd8b3a99a8761039e5.png)

![](../.gitbook/assets/36db3959fc814f9a9bba548374a112e4.png)

## MACHINE ENUMERATION

### WEB FILES

![](../.gitbook/assets/69e06b7c66544af584aa1d718238de36.png)

```text
david:$1$e7NfNpNi$A6nCwOTqrNR2oDuIKirRZ/
```

![](../.gitbook/assets/89b1dc2efeea40d5b5ebbc260cd6a00b.png)

```text
david:Nowonly4me
```

![](../.gitbook/assets/150b8bde22bf4baaae27ede31b3cb88c.png)

![](../.gitbook/assets/b7dbd2110d3a494bad11cb3be83fbb02.png)

![](../.gitbook/assets/77e3f2bf0f2b4425a06166c2f32fc8ee.png)

![](../.gitbook/assets/5d226b4fb32f42769f837bac0b053023.png)

![](../.gitbook/assets/1cf7da4a41184dac89b46151e1d3c166.png)

## LOGIN SSH

![](../.gitbook/assets/ab2e68fd526644d7bc9870fa9d3e115d.png)

## PRIVESC

![](../.gitbook/assets/592545187a054a77b656f68d24da65f7.png)

![](../.gitbook/assets/c1c25e639705432ba9bf7f069e3e8962.png)

![](../.gitbook/assets/0277979988a64ef6bdf2d8fe5adf094d.png)

![](../.gitbook/assets/a4a7604e09334d73b4328d52b65f10e8.png)

![](../.gitbook/assets/21d20329a55e4d81bb221b9a2c35ab0c.png)

## CREDS

```text
root:$6$JS78lx7ObSd/2eY2$zkk.LEer7SmMyeSSm3kbjm/.1LoTrLFeKnpHP43mA/kY/RGNRTcEp96WsD2QZhBYavYOZTSVuSVVMFzUFn86V0:18196:0:99999:7:::
david:$6$maAFQhyFbcK/2XgC$iJUcfeGtIBZFHbE1ugl00Pm9r023byxysujFq3sbEgmA4oP7ivtHYAI3Cww1ET.z9Je3vostL.PxbvD2c6WXk/:18196:0:99999:7:::
```

## FLAGS

### USER

```text
7db0b48469606a42cec20750d9782f3d
```

### ROOT

```text
9aa36a6d76f785dfd320a478f6e0d906
```

