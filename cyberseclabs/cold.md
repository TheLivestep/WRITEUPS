# COLD

![](../.gitbook/assets/d071c0510c8143299acede86b8770c78.png)

## NMAP SCAN

```text
PORT      STATE SERVICE            REASON          VERSION
80/tcp    open  http               syn-ack ttl 127 Apache httpd 2.4.43 ((Win64) OpenSSL/1.1.1g PHP/7.2.30)
|_http-favicon: Unknown favicon MD5: 56F7C04657931F2D0B79371B2D6E9820
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.43 (Win64) OpenSSL/1.1.1g PHP/7.2.30
| http-title: Welcome to XAMPP
|_Requested resource was http://172.31.1.15/dashboard/
135/tcp   open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn        syn-ack ttl 127 Microsoft Windows netbios-ssn
443/tcp   open  ssl/http           syn-ack ttl 127 Apache httpd 2.4.43 ((Win64) 
445/tcp   open  microsoft-ds       syn-ack ttl 127 Microsoft Windows Server 2008 R2 - 2012 microsoft-ds
1243/tcp  open  serialgateway?     syn-ack ttl 127
3389/tcp  open  ssl/ms-wbt-server? syn-ack ttl 127
5500/tcp  open  http               syn-ack ttl 127 Jetty 9.3.6.v20151106
| http-methods: 
|_  Supported Methods: GET
|_http-server-header: Jetty(9.3.6.v20151106)
|_http-title: Error 404 
5985/tcp  open  http               syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
6095/tcp  open  unknown            syn-ack ttl 127
| fingerprint-strings: 
|   GetRequest, HTTPOptions: 
|_    JNB70*
6096/tcp  open  unknown            syn-ack ttl 127
7993/tcp  open  unknown            syn-ack ttl 127
8018/tcp  open  unknown            syn-ack ttl 127
8500/tcp  open  http               syn-ack ttl 127 Samsung AllShare httpd
| http-methods: 
|_  Supported Methods: OPTIONS GET HEAD POST
|_http-title: 404
8581/tcp  open  unknown            syn-ack ttl 127
| fingerprint-strings: 
|   FourOhFourRequest, GetRequest, HTTPOptions, RTSPRequest, SIPOptions: 
|     HTTP/1.1 403 Forbidden
|     Content-Length: true
|_    Forbidden
20007/tcp open  unknown            syn-ack ttl 127
20008/tcp open  unknown            syn-ack ttl 127
47001/tcp open  http               syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49152/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49153/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49154/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49155/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49163/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49192/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49193/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/722324b71ca843ee89487b101e709606.png)

* NOTHING IN GOBUSTER

### PHPINFO

![](../.gitbook/assets/a8de84e911ad4957a595f57e14218388.png)

![](../.gitbook/assets/ceb362f5eef84aa4ab5df4c526d683e4.png)

## SMB ENUMERATION

* DEAD END

![](../.gitbook/assets/dc45b03d59004e79b8980ed9f975cf7a.png)

## PORT 8500 ENUMERATION

### NIKTO

![](../.gitbook/assets/8e5c6dbe5498482799d82dddcd04e6a6.png)

### COLDFUSION

![](../.gitbook/assets/2d329e519c8f496d8550e38166efb305.png)

* ADMIN:ADMIN WORKED

## EXPLOIT \(METASPLOIT\)

![](../.gitbook/assets/c5512459b7474a33a08cc9da5d539051.png)

![](../.gitbook/assets/c3a4abd964e64fcb929e1a0475b6a271.png)

## WINPEAS

![](../.gitbook/assets/05a69f4ffcb744e89c404fd71e5389ea.png)

![](../.gitbook/assets/b1246903744047b99c6b9748d5afca2f.png)

## EXPLOIT

![](../.gitbook/assets/4c9969fc16a14465bcfee7912b73df1b.png)

![](../.gitbook/assets/923cbde43b934d828a22e2b06296ea4c.png)

* The Shell isn´t stable, lets fix

![](../.gitbook/assets/cae1dac0b04b4898bf0c78e88df19f75.png)

## CREDS

```text
Administrator:500:aad3b435b51404eeaad3b435b51404ee:03ffb14a94c1e286a8b2c644376d9074:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
jade:1009:aad3b435b51404eeaad3b435b51404ee:6adfbcc84fab5910245231288dc52d56:::
```

## FLAGS

### USER

```text
cb6d4de6b3ca3b97e7247fd90a3e0c72
```

### ROOT

```text
0ef516f5bd8895026f9e34947233a1e8
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

