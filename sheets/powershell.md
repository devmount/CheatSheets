# PowerShell

## Symlink

Create a symbolic link e.g. for XAMPP's htdocs directory:

```powershell
New-Item -ItemType SymbolicLink -Path '.\symlink-name' -Target "C:\Users\user\data\git\project\"
```

`symlink-name` is the name of the symbolic link. The target is where the symbolic link actually resolves to.

## Free Port 80

Windows sometimes blocks port 80 due to the HTTP Service, which can be stopped with the following command to make port 80 locally available e.g. for WinNMP, wamp or XAMPP.

```powershell
net stop http
```

## Block Windows 10 telemetry

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\DataCollection\ -nameAllowTelemetry -Value 0
Set-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\DiagTrack\ -name Start -Value 4
Set-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Control\WMI\Autologger\Diagtrack-Listener\ -name Start -Value 0
Set-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\wuauserv\ -name Start -Value 4
```

Edit file `%windir%\system32\drivers\etc\hosts` with admin privileges and add:

```plain
# block known windows hosts
0.0.0.0 geo.settings-win.data.microsoft.com.akadns.net
0.0.0.0 db5-eap.settings-win.data.microsoft.com.akadns.net
0.0.0.0 settings-win.data.microsoft.com
0.0.0.0 db5.settings-win.data.microsoft.com.akadns.net
0.0.0.0 asimov-win.settings.data.microsoft.com.akadns.net
0.0.0.0 db5.vortex.data.microsoft.com.akadns.net
0.0.0.0 v10-win.vortex.data.microsoft.com.akadns.net
0.0.0.0 geo.vortex.data.microsoft.com.akadns.net
0.0.0.0 v10.vortex-win.data.microsoft.com
0.0.0.0 v10.events.data.microsoft.com
0.0.0.0 v20.events.data.microsoft.com
0.0.0.0 us.vortex-win.data.microsoft.com
0.0.0.0 eu.vortex-win.data.microsoft.com
0.0.0.0 vortex-win-sandbox.data.microsoft.com
0.0.0.0 alpha.telemetry.microsoft.com
0.0.0.0 oca.telemetry.microsoft.com
0.0.0.0 ceuswatcab01.blob.core.windows.net
0.0.0.0 ceuswatcab02.blob.core.windows.net
0.0.0.0 eaus2watcab01.blob.core.windows.net
0.0.0.0 eaus2watcab02.blob.core.windows.net
0.0.0.0 weus2watcab01.blob.core.windows.net
0.0.0.0 weus2watcab02.blob.core.windows.net
```

See https://www.bsi.bund.de/DE/Service-Navi/Publikationen/Studien/SiSyPHuS_Win10/AP4/SiSyPHuS_AP4_node.html
