# ALGERNON \| 10 POINTS

![](../.gitbook/assets/0c4b2158dddf4961b0bde868ab28d261.png)

## NMAP SCAN

```text
PORT      STATE SERVICE       REASON          VERSION
21/tcp    open  ftp           syn-ack ttl 127 Microsoft ftpd
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
| ftp-syst: 
|_  SYST: Windows_NT
80/tcp    open  http          syn-ack ttl 127 Microsoft IIS httpd 10.0
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
|_http-title: IIS Windows
135/tcp   open  msrpc         syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 127 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds? syn-ack ttl 127
9998/tcp  open  http          syn-ack ttl 127 Microsoft IIS httpd 10.0
|_http-favicon: Unknown favicon MD5: 9D7294CAAB5C2DF4CD916F53653714D5
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Microsoft-IIS/10.0
| http-title: Site doesn't have a title (text/html; charset=utf-8).
|_Requested resource was /interface/root
17001/tcp open  remoting      syn-ack ttl 127 MS .NET Remoting services
```

## PORT 9998

### SMARTERMAIL V.6919 

![](../.gitbook/assets/5abb8de7dd2049d6ad906a7d4f49eb0a.png)

![](../.gitbook/assets/8419cd171de4481e8babbb7a85535c3d.png)

![](../.gitbook/assets/9980692c23fa477fbfc7363576144963.png)

## EXPLOIT

* [https://www.exploit-db.com/exploits/49216](https://www.exploit-db.com/exploits/49216)

![](../.gitbook/assets/b85b291537634887991fb159fbf73c85.png)

* REMEMBER THE NMAP SCAN \(PORT 17001\)

```text
17001/tcp open  remoting      syn-ack ttl 127 MS .NET Remoting services
```

![](../.gitbook/assets/56cb5e209ed24cb48fab0e5b19c6df32.png)

![](../.gitbook/assets/9e1e99ac57bc4b028c1a88d65ab8de20.png)

## PROOF.TXT

```text
4d85d916eef375d96de643a71ead09cb
```

