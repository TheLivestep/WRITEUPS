# RELEVANT

![](../.gitbook/assets/55a0cf6034a74dca8f7b896b8fe94fe2.png)

## NMAP SCAN

```text
PORT      STATE SERVICE       VERSION
80/tcp    open  http          Microsoft IIS httpd 10.0
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
|_http-title: IIS Windows Server
135/tcp   open  msrpc         Microsoft Windows RPC
139/tcp   open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds  Windows Server 2016 Standard Evaluation 14393 microsoft-ds
3389/tcp  open  ms-wbt-server Microsoft Terminal Services
| rdp-ntlm-info: 
|   Target_Name: RELEVANT
|   NetBIOS_Domain_Name: RELEVANT
|   NetBIOS_Computer_Name: RELEVANT
|   DNS_Domain_Name: Relevant
|   DNS_Computer_Name: Relevant
|   Product_Version: 10.0.14393
|_  System_Time: 2020-10-03T23:01:57+00:00
| ssl-cert: Subject: commonName=Relevant
| Not valid before: 2020-07-24T23:16:08
|_Not valid after:  2021-01-23T23:16:08
|_ssl-date: 2020-10-03T23:02:37+00:00; 0s from scanner time.
49663/tcp open  http          Microsoft IIS httpd 10.0
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
|_http-title: IIS Windows Server
49666/tcp open  msrpc         Microsoft Windows RPC
49668/tcp open  msrpc         Microsoft Windows RPC
Service Info: OSs: Windows, Windows Server 2008 R2 - 2012; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: 1h24m00s, deviation: 3h07m51s, median: 0s
| smb-os-discovery: 
|   OS: Windows Server 2016 Standard Evaluation 14393 (Windows Server 2016 Standard Evaluation 6.3)
|   Computer name: Relevant
|   NetBIOS computer name: RELEVANT\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2020-10-03T16:02:00-07:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2020-10-03T23:02:01
|_  start_date: 2020-10-03T22:54:55
```

## SMB EXPLOIT

![](../.gitbook/assets/ef88197e6e7d40b5a8f32b144f66059e.png)

![](../.gitbook/assets/cbdae1026dd64775937fb99bd6d83353.png)

![](../.gitbook/assets/206d0f404eee4bb1920937883f7339e6.png)

## CREDS

```text
bill:Juw4nnaM4n420696969!$$$
bob:!P@$$W0rD!123
```

## EXPLOITATION

![](../.gitbook/assets/a5cbed40bd9d46ff8456f9fb9db93b33.png)

![](../.gitbook/assets/90cf1c92a95940fbba8be920f0facf5a.png)

## PRIVESC

![](../.gitbook/assets/0d3ea4704101463eb6c7bfb8ddf1add6.png)

![](../.gitbook/assets/994e93f0fef643f39dac1e01b0cab6fc.png)

![](../.gitbook/assets/939a849092fd40188ad01d35850ad2b2.png)

![](../.gitbook/assets/40da9640c152417a9013153b8b16a066.png)

![](../.gitbook/assets/c2aa5e90f1a94cb1b53af1a46a36c896.png)

![](../.gitbook/assets/fcef1d3b441f40fdb581d4bb916567da.png)

## ANSWERS

### User Flag

```text
THM{fdk4ka34vk346ksxfr21tg789ktf45}
```

### Root Flag

```text
THM{1fk5kf469devly1gl320zafgl345pv}
```

