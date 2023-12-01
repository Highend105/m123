# Laborübung XY - Mein PC pingt ins Labor

 - Datum: 25.11.2021
 - Name: Max Muster
 - [Link zur Aufgabenstellung](https://gitlab.com/ch-tbz-it/Stud/m129/-/tree/main/20_GNS3%20Einf%C3%BChrung)

---

![GNS3 Screenshot meines Labors](images/Labor0Overview.PNG)

## Cloud
 - br0 192.168.23.0
 - Eigener PC ist via OpenVPN (Layer2) mit br0 verbunden. 

## Config R1
 - [MikroTik CHR 7.1rc6](https://mikrotik.com/download)
 - [GNS3 MikroTik Cloud Hosted Router](https://gns3.com/marketplace/appliances/mikrotik-cloud-hosted-router)
 - 8 Interfaces Enabled
```
/system/identity set name=R1
/ip/address add address=192.168.24.1/24 interface=ether2
/ip/address add address=192.168.23.16/24 interface=ether1
```

## Config VPC 1
- [GNS3 VPCS](https://docs.gns3.com/docs/emulators/vpcs/)
- 1x Ethernet Interface
```
set pcname PC1
# [IP] [MASKE] [GATEWAY]
ip 192.168.24.2 255.255.255.0 192.168.24.1
```

## Config Eigener Laptop
In *cmd.exe* als Admin:
```cmd
route add 192.168.24.0 mask 255.255.255.0 192.168.23.16
```

## Quellen
 - https://www.howtogeek.com/howto/windows/adding-a-tcpip-route-to-the-windows-routing-table/
 - https://wiki.mikrotik.com/wiki/Manual:IP/Address#Example

## Neue Lerninhalte
 - Lokale Route auf auf einem Windows 10 PC konfigurieren
 - MikroTik RouterOS war für mich komplett neue (Keine Erfahrungen)
 - IPv4-Adressen auf RouterOS konfigurieren
 - Erfahrungen zur Bedienung von GNS3 habe ich bereits in der ersten Übung gesammelt. Neu war die "Edit config" funktion. 

## Reflexion
Mithilfe der Übung habe ich nun das Gefühl eine grobe Übersicht über GNS3 zu haben. Der [Kompetenz](../01_Kompetenzmatrix/README.md) *D1G: Ich kann einfache statische Routingtabellen umsetzen.* bin ich nun definitiv einen Schritt näher gekommen. 
Ich fand die Übung sehr einfach und hatte keine grosse Mühe. 
