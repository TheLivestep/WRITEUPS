# HIJACK

![](../.gitbook/assets/1370f48d0ae746c7bf371665a85903eb.png)

## NMAP SCAN

```text
PORT      STATE SERVICE       REASON          VERSION
80/tcp    open  http          syn-ack ttl 127 Apache httpd 2.4.37 ((Win32) OpenSSL/1.1.1a PHP/7.2.13)
|_http-favicon: Unknown favicon MD5: CF2445DCB53A031C02F9B57E2199BC03
|_http-generator: Drupal 8 (https://www.drupal.org)
| http-methods: 
|_  Supported Methods: GET POST HEAD OPTIONS
| http-robots.txt: 22 disallowed entries 
| /core/ /profiles/ /README.txt /web.config /admin/ 
| /comment/reply/ /filter/tips/ /node/add/ /search/ /user/register/ 
| /user/password/ /user/login/ /user/logout/ /index.php/admin/ 
| /index.php/comment/reply/ /index.php/filter/tips/ /index.php/node/add/ 
| /index.php/search/ /index.php/user/password/ /index.php/user/register/ 
|_/index.php/user/login/ /index.php/user/logout/
|_http-server-header: Apache/2.4.37 (Win32) OpenSSL/1.1.1a PHP/7.2.13
|_http-title: Welcome to Hijack | Hijack
135/tcp   open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 127 Microsoft Windows netbios-ssn
443/tcp   open  ssl/http      syn-ack ttl 127 Apache httpd 2.4.37 ((Win32) OpenSSL/1.1.1a PHP/7.2.13)
3306/tcp  open  mysql         syn-ack ttl 127 MariaDB (unauthorized)
3389/tcp  open  ms-wbt-server syn-ack ttl 127 Microsoft Terminal Services
5985/tcp  open  http          syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
47001/tcp open  http          syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49664/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49665/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49666/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49667/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49668/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49669/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49672/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/daf611e21d5143d2be03fce88d3029bb.png)

### USER ENUMERATION

![](../.gitbook/assets/3ad2d8470a724497bb3aac381cb7d1e6.png)

* Error message to the user JACK

![](../.gitbook/assets/51184cff092d43509cb4a2825d9edf00.png)

### DROOPESCAN

![](../.gitbook/assets/f2811f4685914d2ea7a0f853b0afb163.png)

### EXPLOIT DRUPALGEDDON

* [https://wjmccann.github.io/blog/2018/06/02/Drupalgeddon2](https://wjmccann.github.io/blog/2018/06/02/Drupalgeddon2)

![](../.gitbook/assets/ef872487776e499281e8672370213e01.png)

## UPLOAD METERPRETER REVERSE SHELL

![](../.gitbook/assets/cded229f09714a41a4df6f0b173e735e.png)

### LOCAL EXPLOIT SUGGESTER

![](../.gitbook/assets/38cf421807004be89aa929536d6b83d1.png)

![](../.gitbook/assets/c83ffda53a4f43639a2baa89aae8b69f.png)

None exploit worked

## WINPEAS FINDINGS

![](../.gitbook/assets/28e1906de0084047a23137c35f67655d.png)

![](../.gitbook/assets/ea1f1c1b6c6b437098fb31aa416af752.png)

![](../.gitbook/assets/e8579a2ffeee40498963a0681f98258a.png)

![](../.gitbook/assets/4ec369e456b3435f9ec390b519d50e27.png)

![](../.gitbook/assets/540e448c3dfd4dc6873b0863e995cc5c.png)

C:\Program Files\Hijack\Libraries\Custom.dllCustom.dll

![](../.gitbook/assets/f914551d97fd45bc8b6ccd9ea435e992.png)

![](../.gitbook/assets/d5d417a6ca9e40a68e416fbab071355f.png)

![](../.gitbook/assets/c722859e91ce4dcd822ca9d22104b325.png)

![](../.gitbook/assets/eb1216055a234a7d90eac98d63b444d0.png)

## CREDS

```text
Administrator:500:aad3b435b51404eeaad3b435b51404ee:7338b4cc969700678f8b9ae85ed779cb:::
DefaultAccount:503:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
jack:1008:aad3b435b51404eeaad3b435b51404ee:350144b4ec62c791e0a988419eaa3ee5:::QGR54gprPG5SMw3e
WDAGUtilityAccount:504:aad3b435b51404eeaad3b435b51404ee:58f8e0214224aebc2c5f82fb7cb47ca1:::
```

## FLAGS

### USER

```text
f7beb3cc769e0b70c750eab32e3e3c91
```

### ROOT

```text
eaaaed85d047342ef6ac0b2248e9e599
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

