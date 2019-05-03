**1. To list all network interface**
```
snort -W 
```

**2. To perform intrusion detection on interface no. 2 **

```
snort -c C:\Snort\etc\snort.conf -A console -i 2 > alert.log
```
