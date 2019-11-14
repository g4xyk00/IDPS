**1. To list all network interface**
```
snort -W 
```

**2. To perform intrusion detection on interface no. 2**

```
snort -c C:\Snort\etc\snort.conf -A console -i 2 > alert.log
```

**3. To clean Snort logs weekly automatically**

```
schtasks /Create /SC WEEKLY /D WED /TN "Clean Snort Logs" /TR "C:\Users\IEUser\Desktop\snort_log_cleaner.bat" /ST 15:30
```
