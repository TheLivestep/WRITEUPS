# MONITOR

![](../.gitbook/assets/07d791ebcd294f559479c1d0a6e8e051.png)

## NMAP SCAN

```text
PORT      STATE SERVICE       REASON          VERSION
80/tcp    open  http          syn-ack ttl 127 Indy httpd 18.1.38.11958 (Paessler PRTG bandwidth monitor)
|_http-favicon: Unknown favicon MD5: 36B3EF286FA4BEFBB797A0966B456479
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: PRTG/18.1.38.11958
| http-title: Welcome | PRTG Network Monitor
|_Requested resource was /index.htm
|_http-trane-info: Problem with XML parsing of /evox/about
135/tcp   open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 127 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds  syn-ack ttl 127 Windows Server 2016 Datacenter 14393 microsoft-ds
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
49668/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49669/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49675/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
49677/tcp open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/d8c1590f19704d9485bcebf46f6d3fcb.png)

## SMB ENUMERATION

![](../.gitbook/assets/52fb4f7c17e04e8f9ce29c12d5e019a7.png)

![](../.gitbook/assets/2baa1be7851443dba097fe7b4151afa0.png)

### DEV06.ZIP

![](../.gitbook/assets/8e85b3d6a0c444f680ef96ffb7ca47a2.png)

* DB.SQLITE3

![](../.gitbook/assets/8f4890c127d74dfbb8c90e74a6d72b6b.png)

![](../.gitbook/assets/f25227c26c45426d9ab33919662d0ef3.png)

```text
django:Se7vmMqP0al
```

### SEE IF WORKS IN SMB

![](../.gitbook/assets/540283263aa64f1d80773373b8ad8d61.png)

### WORKS IN PRTG NETWORK MONITOR?

```text
django:Se7vmMqP0al    //DON'T WORK

prtgadmin:Se7vmMqP0al    //WORKS
```

![](../.gitbook/assets/806c9d590c9049c78b6ef8fef30e2ac0.png)

## EXPLOIT

* [https://www.exploit-db.com/exploits/46527](https://www.exploit-db.com/exploits/46527)
* RETRIEVE COOKIES FROM BURPSUITE

![](../.gitbook/assets/af9fafee32774104b095059e3d1e1fdf.png)

```text
_ga=GA1.1.143271405.1615749717; _gid=GA1.1.684995975.1615749717; OCTOPUS1813811958=ezk4NDE1NDdBLTRFRTItNDU3RC04Q0I0LUZFRTcwOTg2MkY0Mn0%3D
```

![](../.gitbook/assets/4ddfc95a90ee485089b7ac27bcace3d7.png)

![](../.gitbook/assets/36d6a39dba4642e3b5434bb572bd3f19.png)

```text
pentest:P3nT3st!
```

### LOGIN

```text
xfreerdp /u:pentest /p:P3nT3st! /cert:ignore /v:172.31.1.21
```

![](../.gitbook/assets/1001a38f387b41a89641816ffbce879c.png)

![](../.gitbook/assets/7ddea1469d3a4102b0fcc15d9d6fa40d.png)

![](../.gitbook/assets/8b5dfef3d64a4c5081cdd00f6bb3d859.png)

## FLAGS

### USER

```text
1a69b557236ac8373ded3f1dc25e0d8c
```

### ROOT

```text
ba80fae4e8e73b6d013ad6f3bd8193b2
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

