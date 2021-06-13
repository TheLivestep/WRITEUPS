# SHOCKER / OSCP PREP

![](../.gitbook/assets/e88d72ce99064270942c72aed27e323c.png)

## NMAP SCAN

```text
PORT     STATE SERVICE REASON         VERSION
80/tcp   open  http    syn-ack ttl 63 Apache httpd 2.4.18 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Site doesn't have a title (text/html).
2222/tcp open  ssh     syn-ack ttl 63 OpenSSH 7.2p2 Ubuntu 4ubuntu2.2 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 c4:f8:ad:e8:f8:04:77:de:cf:15:0d:63:0a:18:7e:49 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD8ArTOHWzqhwcyAZWc2CmxfLmVVTwfLZf0zhCBREGCpS2WC3NhAKQ2zefCHCU8XTC8hY9ta5ocU+p7S52OGHlaG7HuA5Xlnihl1INNsMX7gpNcfQEYnyby+hjHWPLo4++fAyO/lB8NammyA13MzvJy8pxvB9gmCJhVPaFzG5yX6Ly8OIsvVDk+qVa5eLCIua1E7WGACUlmkEGljDvzOaBdogMQZ8TGBTqNZbShnFH1WsUxBtJNRtYfeeGjztKTQqqj4WD5atU8dqV/iwmTylpE7wdHZ+38ckuYL9dmUPLh4Li2ZgdY6XniVOBGthY5a2uJ2OFp2xe1WS9KvbYjJ/tH
|   256 22:8f:b1:97:bf:0f:17:08:fc:7e:2c:8f:e9:77:3a:48 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBPiFJd2F35NPKIQxKMHrgPzVzoNHOJtTtM+zlwVfxzvcXPFFuQrOL7X6Mi9YQF9QRVJpwtmV9KAtWltmk3qm4oc=
|   256 e6:ac:27:a3:b5:a9:f1:12:3c:34:a5:5d:5b:eb:3d:e9 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIC/RjKhT/2YPlCgFQLx+gOXhC6W3A3raTzjlXQMT8Msk
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
```

## PORT 80 ENUMERATION

### GOBUSTER

![](../.gitbook/assets/8d7ea0e2cc6842f692a5be7eef93f5c9.png)

### NIKTO

![](../.gitbook/assets/3017b924626b4bbb96d47799c3fed681.png)

## SHELLSHOCK

![](../.gitbook/assets/7f8b944a7b6e44f0bc0b4ed8758ed056.png)

![](../.gitbook/assets/901f34b9dcc04f74b939f4d64ad9491c.png)

## EXPLOIT

![](../.gitbook/assets/c98e759180134d879cd838fe7358451f.png)

![](../.gitbook/assets/00e102fb5f984df99698c1f2b9a19434.png)

## PRIVESC

* There are some Ways
* LXD GROUP 

![](../.gitbook/assets/d72bd20a03214ca592f1255c192d8960.png)

* SUDO PERL

![](../.gitbook/assets/4b2d72cb531c4e93b63742e626a510ee.png)

![](../.gitbook/assets/d592b2607a2141e98ba643e84b552a5d.png)

## FLAGS

### USER

```text
b0ccf8c6ae90e4f2c7f431204bfff8f0
```

### ROOT

```text
5f72930ff2d95da9a2adc930a3f2d29b
```

## SHADOW

```text
root:$6$BVgS5ne0$Q6rV3guK7QQUy7uRMwbQ3vv2Y5I9yQUhIzvrIhuiDso/o5UfDxZw7MMq8atR3UdJjhpkFVxVD0cVtjXQdPUAH.:17431:0:99999:7:::
shelly:$6$aYLAoDIC$CJ8f8WSCT6GYmbx7x8z5RfrbTG5mpDkkJkLW097hoiEw3tqei2cE7EcUTYdJTVMSa3PALZeBHjhiFR8Ba5jzf0:17431:0:99999:7:::
```

