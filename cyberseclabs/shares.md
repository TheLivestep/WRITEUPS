# SHARES

![](../.gitbook/assets/4521d14c0ece414bbafcb4c899d7f587.png)

## NMAP SCAN

```text
PORT      STATE SERVICE  REASON  VERSION
21/tcp    open  ftp      syn-ack vsftpd 3.0.3
80/tcp    open  http     syn-ack Apache httpd 2.4.29 ((Ubuntu))
| http-methods: 
|_  Supported Methods: POST OPTIONS HEAD GET
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: Pet Shop
111/tcp   open  rpcbind  syn-ack 2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100000  3,4          111/tcp6  rpcbind
|   100000  3,4          111/udp6  rpcbind
|   100003  3           2049/udp   nfs
|   100003  3           2049/udp6  nfs
|   100003  3,4         2049/tcp   nfs
|   100003  3,4         2049/tcp6  nfs
|   100005  1,2,3      35230/udp   mountd
|   100005  1,2,3      39893/tcp   mountd
|   100005  1,2,3      49564/udp6  mountd
|   100005  1,2,3      55855/tcp6  mountd
|   100021  1,3,4      37421/udp   nlockmgr
|   100021  1,3,4      44101/tcp6  nlockmgr
|   100021  1,3,4      46179/tcp   nlockmgr
|   100021  1,3,4      54169/udp6  nlockmgr
|   100227  3           2049/tcp   nfs_acl
|   100227  3           2049/tcp6  nfs_acl
|   100227  3           2049/udp   nfs_acl
|_  100227  3           2049/udp6  nfs_acl
2049/tcp  open  nfs_acl  syn-ack 3 (RPC #100227)
27853/tcp open  ssh      syn-ack OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
39893/tcp open  mountd   syn-ack 1-3 (RPC #100005)
43463/tcp open  mountd   syn-ack 1-3 (RPC #100005)
46179/tcp open  nlockmgr syn-ack 1-4 (RPC #100021)
48445/tcp open  mountd   syn-ack 1-3 (RPC #100005)
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/1d7f44fd1618481bbe45515fe6105d84.png)

## NFS ENUMERATION

![](../.gitbook/assets/45b3d9032f864ee69512b610ec2528be.png)

### MOUNT

![](../.gitbook/assets/c55884c967304886a330ec925dcf8fbe.png)

```text
-----BEGIN RSA PRIVATE KEY-----
Proc-Type: 4,ENCRYPTED
DEK-Info: AES-128-CBC,8D55B7449F8965162DA3B7F2F017FC21

2lI1tgSF61MjFg2Er22GWr9hImJbuZ01I556yFoLAGNj/95ZB2H8Er9u8wfMgr8z
uB8Yuw2GmO0jJguQ4CK36kDLT/hpG5AW5WfHASzePHx58Ol2hrH+2e5IAoIwcVmi
bFN3zIYYCznn6bIvRaqwkuxaD01EG8IPxgAvm0Nr3sP539wngplyf7/+xqvPyT18
jT058FEMPFmeb+V0MHczlNWOW6wrGnxQAea2ON+IUwiSsTVSLv4QLGVWF8Lcualy
t4+4Kr47gdlxRh9HcNDztfIztimMdGp8AdV5z4KDKyL6FUVfmZqC2nxhbFUKtF7k
su7qHGpV9p9Pkglx+/rUq9NeifFcRGrhsOWctUXmWJ7BbmrqFgw1+X8ui6A/uttE
R8hEblI4obffLnGDrAO4wuH+qtA2oelwwjl/JxyqwbGH4RGAW/4AseqDzQ6RpfgQ
Sq8wBPb5MMp2ZKEzEl8qcWcwS1FCGz/VPHpnEYwfpFlcJ1kpqkiT5gmNrDFauN1m
upeSS7T5iAeHHmskbHJfNNSGYjSbTRzCSFlq2vCNXGte7jta34YCVucNHBIUR/2y
GLrm3CmVYPrjdw0irwDt+uepPfUyQQLhSqiZdbyGiljlUeij5+zJax7tOjlBBjBS
Y0rMRwiG8FGDEBbSmDZk30qB3Qb9TQcaqe9Wi/liFuxVyfbukiGW2b65JGbd7R1q
Vh6pKw4Hd35iGmVskme7evsSupEMOu9fKsJAkIrQTxadpU8wG2wkp0NTM7fh3aut
TDGKorRXOXj+cV6zehjXUYyUTesTMDh9EUVmHuixvIFX8V3w562BV28murByt7I+
ubvmZxjvh51nzpOJa4g61tnj/4OCbhFCEK4nsExh0HS11WeDAvueDauLk2Wgiw/z
/yyssrshPiXe/vxYGFJlHelyDaUSwpdrZ0AGzwUutN0rOrh3yS6yTDH2raLSa76y
e1bxe+rh2Q/iEhzqa1RbWrg7fA+5FJRLAZdYlaqlEsVt81nw4mdBCpjEbUl19egF
xIqogCAilFWvnZQ4f12JPmk0mke84idw76+SdBeof18gGiR3mWn3IyoFLRacMs5N
4zrNBXOGCVVzXCoo88ioYw1I91O57c0vbx8S40SbIevUprphf3VTZlyrRxw2AB/R
zclXHN/fEewst2maxauD+32Krm1uvTcCNk3CNre7NwPb6tB0rY3R3E7h2S/MKt0Y
eZKbFFmLwnokHqzSI8uIy8wrPj6H9R+wxT0+/KPyi3L7JIbParsHO4flBx1sMCUl
jlSNW/3J2ADP7QKA5AyjVcsIbp/aXyeJKCtglRc4Yl8mEmCroe61pCDO0mnatWxF
Y9/z6VRC61sjO4T1xYcGFSlVeXANuN8TYR8mUyvruG8OoNQ65RvgxSCRPzFe4EAm
xmXIQ4pDW59LSO7PnPdjsGN8eY7xTnG5509DYK6FoUC0T8hjp/wR9ucKDDqQoXpW
BM9cM5IPltG+wAlP39EbGMinnqgqDazWAk/wSKo4ieGLnWcNORe7Ti299tImCy0l
8zJWICDbH7bSMYyVPlWBrgUBWQ6xFI55iKdhjhlQdblZI04DoSathKFe+Khjb8bi
-----END RSA PRIVATE KEY-----
```

![](../.gitbook/assets/6154c927f4e449478088a77ee1c27388.png)

![](../.gitbook/assets/f19c8369940f43238230240c396557f2.png)

```text
hello6
```

## LOGIN SSH

![](../.gitbook/assets/d4ee6f6f235840ccbf8dbe909b645dcb.png)

## LATERAL MOVEMENT

![](../.gitbook/assets/5c8d76058b1f49a59301573e8c7f0a16.png)

## PRIVESC

![](../.gitbook/assets/7bd4823db89f4676a899c246e1fdcc7a.png)

## CREDS

```text
root:$6$N24s.PAw$sR4C1sCVgRhq7Xde2bOKLPvLFExxF9FfQkBaqlzGR.n6XGIZ5pu5fJ6tN8f/TryZZ199bkgcOnEzwXDyZkWke/:18354:0:99999:7:::
amir:$6$n/DQ2xPW$uyEDWuqWc4zBx9oN8Bd0niNzzve1LZ54uHuxJledAN1ZxGYwdVxnw34gKbu3BZuZb8CmjE8ZGtCsSMz.3uBFK1:18354:0:99999:7:::
amy:$6$hDHnGGlJ$C0wRAmI9tpp94U1WAyKVTYSTDkHDRskCW972KAFji0.n/MSMBg0lnXV5LnOdDJ32NtuUEXY4ZHIyc5DhkEcRI1:18354:0:99999:7:::
```

## FLAGS

### USER

```text
dc17a108efc49710e2fd5450c492231c
```

### ROOT

```text
b910aca7fe5e6fcb5b0d1554f66c1506
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

