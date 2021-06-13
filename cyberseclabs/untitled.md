# ENGINE

![](../.gitbook/assets/4ad585bd6edc4ff59c4ee85f6dfec8e2.png)

## NMAP SCAN

```text
PORT      STATE SERVICE            REASON          VERSION
80/tcp    open  http               syn-ack ttl 127 Microsoft IIS httpd 8.5
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/8.5
|_http-title: IIS Windows Server
135/tcp   open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn        syn-ack ttl 127 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds       syn-ack ttl 127 Microsoft Windows Server 2008 R2 - 2012 microsoft-ds
3389/tcp  open  ssl/ms-wbt-server? syn-ack ttl 127
5985/tcp  open  http               syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49154/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49155/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49164/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/2c2c34f636874953913561b147a25702.png)

![](../.gitbook/assets/3d7d01138b074a0993fb1e70d59f6490.png)

### GOBUSTER

```text
gobuster dir -u http://172.31.1.16 -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -x asp,aspx,txt -t 20
```

#### /BLOG

![](../.gitbook/assets/238516cc43e5458097b25c27bd05abcf.png)

![](../.gitbook/assets/3a3d02626fb540cf94b3d1511c0166e5.png)

![](../.gitbook/assets/ec4f64e0572b44df9d1e8fd06d8387ad.png)

## EXPLOIT

* [https://www.exploit-db.com/exploits/47010](https://www.exploit-db.com/exploits/47010)

![](../.gitbook/assets/5b7e1ceaab5b453a88886047c3ecbec6.png)

1. Using /Blog in Command

![](../.gitbook/assets/fbc61841961f4f50b816ca01f69fa3a5.png)

1. Using BURPSUITE, to change the Ip

![](../.gitbook/assets/9b9878db64a041be804526a77937ba96.png)

![](../.gitbook/assets/4edc4d7a23114e7c94318b1478ecce3b.png)

![](../.gitbook/assets/370a56ae9ba241bba1baa9bf2cbb9cfd.png)

![](../.gitbook/assets/0d01774a0448473bbf65d41962d95582.png)

1. Because the shell isn´t stable i upload a meterpreter reverse shell

![](../.gitbook/assets/8f1d01161f3945e58feb4e9730e72f16.png)

![](../.gitbook/assets/7cb6994856db4564b39acb7f95c7f0dd.png)

## WINPEAS

![](../.gitbook/assets/7e2d2e224dd846559b3667b3faa910ca.png)

![](../.gitbook/assets/a0c4a7047ba349b3b287c049b9cfe770.png)

```text
Administrator:PzCEKhvj6gQMk7kA
```

## PRIVESC

![](../.gitbook/assets/588143f664004b61a25157ce876a90bf.png)

OR

```text
xfreerdp /u:administrator /p:PzCEKhvj6gQMk7kA /cert:ignore /v:172.31.1.16
```

![](../.gitbook/assets/59fd3376c4c14158867691e475edc0e7.png)

## FLAGS

### USER

```text
150688cfd5d47037eda7a9bb589c8743
```

### ROOT

```text
d345d4ac0d810fcfb63b8be2b7e3bb71
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

