# LEAKAGE

![](../.gitbook/assets/77fc9d7eaa2c47b584c99141f2288cc9.png)

## NMAP SCAN

```text
PORT     STATE SERVICE REASON         VERSION
22/tcp   open  ssh     syn-ack ttl 63 OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 7a:5a:dd:ad:4c:6f:6c:4a:60:06:4f:46:53:77:96:15 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCe9jN7mwM22qkU8huzXMh10ko6SuWXrJQ6T81eSVJlCXqaK+o0lODlx3sS0cUip/B8K10tnhzQ3Q02zEmTz6MV0B5Sn1yFsPgKxOML/Qwb0JGhfGyDjKPbJ65q7PfbQuZIAvOZhb5gPKkq4y5vixzgKj/c1fyou4aereyp7KezyuBUAkT2H3oRduRPq9OUenEzTZjXb+zsol1fDu/8GufrFx4IIdI/4FyV9x9VYHw686wa6D2gT/68YtS24V8tAbywD4A8liLjJWH5RK2dKgQEzjzlte/GOAXMzpyGlo5Uwxd5KY9u5PjgsSHh3w9Rb6EMZjeELik3RTGh4NM4Edeh
|   256 83:ff:c2:72:62:11:4a:86:f9:bf:41:2c:b6:2b:97:a4 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBFpjeHu3ddMRC0ccsLaHXZQVean4YktBPTxna1BbSvA2hEAxonuOd+khCxkwzK1UO9bcMyK64rHejrqkG3Ud0J0=
|   256 bf:93:3b:d1:6b:ea:32:99:6c:46:75:7b:e2:f1:8a:d9 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIFmn8hCki3Se/OK4cfSktr1fVyb3WDxTzZzy5rDHtV2y
80/tcp   open  http    syn-ack ttl 63 nginx
|_http-favicon: Unknown favicon MD5: F7E3D97F404E71D302B3239EEF48D5F2
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
| http-robots.txt: 57 disallowed entries (40 shown)
| / /autocomplete/users /search /api /admin /profile 
| /dashboard /projects/new /groups/new /groups/*/edit /users /help 
| /s/ /snippets/new /snippets/*/edit /snippets/*/raw 
| /*/*.git /*/*/fork/new /*/*/repository/archive* /*/*/activity 
| /*/*/new /*/*/edit /*/*/raw /*/*/blame /*/*/commits/*/* 
| /*/*/commit/*.patch /*/*/commit/*.diff /*/*/compare /*/*/branches/new 
| /*/*/tags/new /*/*/network /*/*/graphs /*/*/milestones/new 
| /*/*/milestones/*/edit /*/*/issues/new /*/*/issues/*/edit 
| /*/*/-/merge_requests/new /*/*/-/merge_requests/*.patch 
|_/*/*/-/merge_requests/*.diff /*/*/-/merge_requests/*/edit
| http-title: Sign in \xC2\xB7 GitLab
|_Requested resource was http://172.31.1.6/users/sign_in
|_http-trane-info: Problem with XML parsing of /evox/about
8060/tcp open  http    syn-ack ttl 63 nginx 1.16.1
| http-methods: 
|_  Supported Methods: GET HEAD POST
|_http-server-header: nginx/1.16.1
|_http-title: 404 Not Found
9094/tcp open  unknown syn-ack ttl 63
```

## PORT 80 ENUMERATION

![](../.gitbook/assets/e1fcef04e8014ed099649edf701faca8.png)

![](../.gitbook/assets/51675d215aa84c5ab0162a0d86249571.png)

### REGISTERING

![](../.gitbook/assets/071b0c10e3434a34aac15b7d52f5770f.png)

![](../.gitbook/assets/287e2ba7c4c74df59d79fdd5182235e4.png)

### PROJECTS

![](../.gitbook/assets/b9c6f0d822c041a9aa963f58c2d440c8.png)

#### CMS

* config.php

![](../.gitbook/assets/182252f6861043059249578fd67e9e62.png)

![](../.gitbook/assets/8945fc116a36498795cbd25b6d45f258.png)

![](../.gitbook/assets/393fd03731664405b99786ceb652e725.png)

```text
jonathan@rPHAKWAgMZtjr9at
```

![](../.gitbook/assets/5f7f4e0652784e46ba83cf812bc3e792.png)

![](../.gitbook/assets/8f1db497ce0340f4a3dbe75ab86a19fb.png)

* id\_rsa ENCRYPTED

```text
-----BEGIN RSA PRIVATE KEY-----
Proc-Type: 4,ENCRYPTED
DEK-Info: AES-128-CBC,8195A08A6A205E425326C0C3FDC09F06

Xv4NSHR4axwHPGs0La0NztG45JBvlIgDFtPs0okJw/AyskKSNrAmIkzdp3WXuETG
tal1ODeucnIlipYnXPSOuzJAchk3lkyUqpMSB+N8ljCvLnTEY0FZU0HsHkaPWvPB
qTn4tgtrgzO2hI2S/WV5q43vmmTbC7pZraMdGakr/uncbav59CnQl4mr7uygYYuq
CoN26OFPefFA5KIvUWURZfMgaMjFqP0udrj2IXh0LJxpKlrFGItST2KscFcustvS
VU9JQsWoJ9O4JUcb9dUaxU1LYmfFv2PcogN0joipCbPppNL1iBkwusRoCVCFGIM9
7mAccCZBc53t6mV8OCpBXxDmm5V4HrQGnMeZBoguuPPYR54KTbF9qhU4ZOTODVzp
ADP32fau3m13UqzZsBShOsrR6wC6UgtvZ1nuELMjl0GcCZ2UAScD97hy+7vV4O22
umIRm9wQjSWBtY6cZe47usTuzyXPzpaqtZl3Em+2BzUE+JEvETmZ0+EYgGrZ6/qK
dmjt4a4gCIh4VvLxHUnyuL47V2zuKFGT7mmowUXM+g266Q0xjatdHxTbMPCr3T8f
GCW5GxYcB7yjB+jWqr+jtE45F4LG0BY0UMQzZgJ0zT+ZgbafJMd/P8qd6A1hCIqH
cNLBt3aenK8E5/ZFVbTJzFSa7NdEsZNuCAFkLN2Dh8ZZ6811orIMrKDAkVmbf3Fj
I4n/YxWtz3IrmhR/0B5D1+JZW2CkRfzJe/htLAYkOY/G8RdysAyGjLrBegyxDSHD
k1Zr25nc0URcZtDlAvVHd2i/IWfIpsIF+ZcY4+QGx5yH0NNP42K+UMJFSnWdL0CN
K1KiROGNBdNYsP5A0e/Odasz7pnev8w2KdW0pOEAd8ORBLtWcwoYectFdaR8nRhM
8UiOhfk9Y0FsrPb7t9KcjkzWEgZjNbMZrQTyoEaqLGXTO0ESS/gkicz9rFUU7qmQ
u+HWltL3+5C5VO7tvq21MPt7KZ2r0AbxRxRU+Xk55++vJSkNMtONpSaeXe2/+5Fj
w6BOT5KO2eiUwo2C7GBl+aJl8K7a2gtZaOw5KJYGUfs+qcoLo1V2k0qicLvldJnP
11nnwU3mCNtq2SHvwriDIkx0jT7s1s+rlT8E9ySJhyG+9KUdaDnbC5gz9j5pm/QA
CiBQV+czK3/LBt3+dEjyJXP+RjcdDi60Owiu6egrfF5Pms9XY7Z8PG+oHlpH+B6k
IhYbEL/qPcLkHjuwHTFLUICsX/HuBGMBCY6karuf+6AwpaohMT9Wn+Es7UZ3FBSz
BDwZAE68fyOLmJgFY7SlIXQhQcP7dVTc5EaIBCWKIoeLJNEqwKgkLxMxybnz21vk
UdZ6ZOVg49VNb15omZtiEXA2L46BhtxHJEiJR9lKfYw+20++XjwKyy7RPo/vE5Yn
FJgDajrLEvtNxEZ0B/tNdxI61lkOK8+GXRCQU+9WFtsl+I46Ut24L3XUDQQmPyWk
boDDkgA0WnM08LDbA3FK5GBPB6go2HTZ/bidzABx9KpkaJfHzZgQzEMSfTz2Melq
jj5rxHXKJDLV/cLhGAXmTqfhknTbHvBzzfs0GMkZICXlDSjvuDriJd+1DswKckaV
-----END RSA PRIVATE KEY-----
```

* CRACK ID\_RSA

![](../.gitbook/assets/9e7432b90413405c9dbcd4919b813535.png)

```text
scooby
```

## LOGIN SSH

![](../.gitbook/assets/621d06b0486d4a15a334aa6e0a4ad480.png)

## LINPEAS FINDINGS

* LXD GROUP
* SUDO 1.8.21p2
* WTF?

![](../.gitbook/assets/086cf22dcd4547b08e58c8fe77910c78.png)

![](../.gitbook/assets/9197cd5d46a245c88c61d05e0c35cc71.png)

## GROUP LXD PRIVESC

* [https://www.hackingarticles.in/lxd-privilege-escalation/](https://www.hackingarticles.in/lxd-privilege-escalation/)

```text
git clone  https://github.com/saghul/lxd-alpine-builder.git
cd lxd-alpine-builder
./build-alpine
```

![](../.gitbook/assets/20982566fecf4a82b2a8ac8dbea7ae07.png)

* If you encounter an error

![](../.gitbook/assets/56b67944034241619c2cee260d30a9aa.png)

![](../.gitbook/assets/27109016260d4929b2c5ab88b9bf15d2.png)

## FLAGS

### USER

```text
43d72a36c51d97e8aef93a6e90e4e493
```

### ROOT

```text
933f9f8ba314ab4c8c332ccbbb5f2af1
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

