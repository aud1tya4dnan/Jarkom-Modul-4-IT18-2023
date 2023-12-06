# Jarkom-Modul-4-IT18-2023

# Praktikum 4

## VLSM Dengan GNS

Langkah awal yang kami ambil adalah menentukan subnet dalam topologi. Karena menggunakan metode VLSM, kami mengidentifikasi setiap host yang terhubung ke antarmuka router dan menghitung jumlah IP yang diperlukan. Berikut adalah gambaran dari pembagian subnet.

![Untitled](https://github.com/aud1tya4dnan/Jarkom-Modul-4-IT18-2023/assets/107627453/faf58631-8fcb-44cc-aca6-4c233ed4ce5e)

Setelah menentukan pembagian subnet, kami juga telah melakukan perhitungan untuk alokasi IP. Berikut adalah hasil perhitungan tersebut

| Nama Subnet | Rute | Jumlah IP | Length | NetMask | Network ID | Broadcast | Usable IP Range |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Total |  | 4255 | /19 |  |  |  |  |
| A18 | Fern-Switch4-LaubHills-Switch4-AppetitRegion | 1023 | /21 | 255.255.248.0 | 192.242.0.0 | 192.242.7.255 | 192.242.0.1-192.242.7.254 |
| A1 | Lugner-Switch10-TurkRegion | 1001 | /22 | 255.255.252.0 | 192.242.8.0 | 192.242.11.255 | 192.242.8.1-192.242.11.254 |
| A19 | Flamme-Switch5-RohrRoad | 1001 | /22 | 255.255.252.0 | 192.242.12.0 | 192.242.15.255 | 192.242.12.1-192.242.15.254 |
| A9 | Heiter-Switch8-Sein-Switch8-RiegelCanyon | 512 | /22 | 255.255.252.0 | 192.242.16.0 | 192.242.19.255 | 192.242.16.1-192.242.19.254 |
| A6 | Linie-Switch11-GranzChannel | 255 | /23 | 255.255.254.0 | 192.242.20.0 | 192.242.21.255 | 192.242.20.1.-192.242.21.254 |
| A2 | Lugner-Switch9-GrobeForest | 251 | /24 | 255.255.255.0 | 192.242.22.0 | 192.242.22.255 | 192.242.22.1-192.242.22.254 |
| A13 | Denken-Switch2-RoyalCapital-Switch2-WileRegion | 127 | /24 | 255.255.255.0 | 192.242.23.0 | 192.242.23.255 | 192.242.23.1-192.242.23.254 |
| A8 | Lawine-Switch7-Heiter-Switch7-BredtRegion | 31 | /26 | 255.255.255.192 | 192.242.24.0 | 192.242.24.63 | 192.242.24.1-192.242.24.62 |
| A15 | Frieren-Switch3-LakeKorridor | 25 | /27 | 255.255.255.224 | 192.242.24.64 | 192.242.24.95 | 192.242.24.65-192.242.24.94 |
| A21 | Himmel-Switch6-SchwerMountains | 6 | /29 | 255.255.255.248 | 192.242.24.96 | 192.242.24.103 | 192.242.24.97-192.242.24.102 |
| A10 | Eisen-Switch1-Richter-Switch1-Revolte | 3 | /29 | 255.255.255.248 | 192.242.24.104 | 192.242.24.111 | 192.242.24.105-192.242.24.110 |
| A3 | Eisen-Lugner | 2 | /30 | 255.255.255.252 | 192.242.24.112 | 192.242.24.115 | 192.242.24.113-192.242.24.114 |
| A4 | Eisen-Switch0-Stark | 2 | /30 | 255.255.255.252 | 192.242.24.116 | 192.242.24.119 | 192.242.24.117-192.242.24.118 |
| A5 | Eisen-Linie | 2 | /30 | 255.255.255.252 | 192.242.24.120 | 192.242.24.123 | 192.242.24.121-192.242.24.122 |
| A7 | Linie-Lawine | 2 | /30 | 255.255.255.252 | 192.242.24.124 | 192.242.24.127 | 192.242.24.125-192.242.24.126 |
| A11 | Eisen-Aura | 2 | /30 | 255.255.255.252 | 192.242.24.128 | 192.242.24.131 | 192.242.24.129-192.242.24.130 |
| A12 | Aura-Denken | 2 | /30 | 255.255.255.252 | 192.242.24.132 | 192.242.24.135 | 192.242.24.133-192.242.24.134 |
| A14 | Aura-Frieren | 2 | /30 | 255.255.255.252 | 192.242.24.136 | 192.242.24.139 | 192.242.24.137-192.242.24.138 |
| A16 | Frieren-Flamme | 2 | /30 | 255.255.255.252 | 192.242.24.140 | 192.242.24.143 | 192.242.24.141-192.242.24.142 |
| A17 | Flamme-Fern | 2 | /30 | 255.255.255.252 | 192.242.24.144 | 192.242.24.147 | 192.242.24.145-192.242.24.146 |
| A20 | Flamme-Himmel | 2 | /30 | 255.255.255.252 | 192.242.24.148 | 192.242.24.151 | 192.242.24.149-192.242.24.150 |

Lalu kita membagi IP seperti berikut 

| Nama Subnet | Rute | Usable IP Range | IP | NetMask |
| --- | --- | --- | --- | --- |
| Total |  |  |  |  |
| A18 | AppetitRegion | 192.242.0.1-192.242.7.254 | 192.242.0.1 | 255.255.248.0 |
|  | Fern |  | 192.242.0.2 |  |
|  | LaubHills |  | 192.242.0.3 |  |
| A1 | Lugner | 192.242.8.1-192.242.11.254 | 192.242.8.1 | 255.255.252.0 |
|  | TurkRegion |  | 192.242.8.2 |  |
| A19 | Flamme | 192.242.12.1-192.242.15.254 | 192.242.12.1 | 255.255.252.0 |
|  | RohrRoad |  | 192.242.12.2 |  |
| A9 | Heiter | 192.242.16.1-192.242.19.254 | 192.242.16.1 | 255.255.252.0 |
|  | Sein |  | 192.242.16.2 |  |
|  | RiegelCanyon |  | 192.242.16.3 |  |
| A6 | Linie | 192.242.20.1.-192.242.21.254 | 192.242.20.1 | 255.255.254.0 |
|  | GranzChannel |  | 192.242.20.2 |  |
| A2 | Lugner | 192.242.22.1-192.242.22.254 | 192.242.22.1 | 255.255.255.0 |
|  | GrobeForest |  | 192.242.22.2 |  |
| A13 | Denken | 192.242.23.1-192.242.23.254 | 192.242.23.1 | 255.255.255.0 |
|  | RoyalCapital |  | 192.242.23.2 |  |
|  | WileRegion |  | 192.242.23.3 |  |
| A8 | Lawine | 192.242.24.1-192.242.24.62 | 192.242.24.1 | 255.255.255.192 |
|  | Heiter |  | 192.242.24.2 |  |
|  | BredtRegion |  | 192.242.24.3 |  |
| A15 | Frieren | 192.242.24.65-192.242.24.94 | 192.242.24.66 | 255.255.255.224 |
|  | LakeKorridor |  | 192.242.24.67 |  |
| A21 | Himmel | 192.242.24.97-192.242.24.102 | 192.242.24.97 | 255.255.255.248 |
|  | SchwerMountains |  | 192.242.24.98 |  |
| A10 | Eisen | 192.242.24.105-192.242.24.110 | 192.242.24.105 | 255.255.255.248 |
|  | Richter |  | 192.242.24.106 |  |
|  | Revolte |  | 192.242.24.107 |  |
| A3 | Eisen | 192.242.24.113-192.242.24.114 | 192.242.24.113 | 255.255.255.252 |
|  | Lugner |  | 192.242.24.114 |  |
| A4 | Eisen | 192.242.24.117-192.242.24.118 | 192.242.24.117 | 255.255.255.252 |
|  | Stark |  | 192.242.24.118 |  |
| A5 | Eisen | 192.242.24.121-192.242.24.122 | 192.242.24.121 | 255.255.255.252 |
|  | Linie |  | 192.242.24.122 |  |
| A7 | Linie | 192.242.24.125-192.242.24.126 | 192.242.24.125 | 255.255.255.252 |
|  | Lawine |  | 192.242.24.126 |  |
| A11 | Eisen | 192.242.24.129-192.242.24.130 | 192.242.24.129 | 255.255.255.252 |
|  | Aura |  | 192.242.24.130 |  |
| A12 | Aura | 192.242.24.133-192.242.24.134 | 192.242.24.133 | 255.255.255.252 |
|  | Denken |  | 192.242.24.134 |  |
| A14 | Aura | 192.242.24.137-192.242.24.138 | 192.242.24.137 | 255.255.255.252 |
|  | Frieren |  | 192.242.24.138 |  |
| A16 | Frieren | 192.242.24.141-192.242.24.142 | 192.242.24.141 | 255.255.255.252 |
|  | Flamme |  | 192.242.24.142 |  |
| A17 | Flamme | 192.242.24.145-192.242.24.146 | 192.242.24.145 | 255.255.255.252 |
|  | Fern |  | 192.242.24.146 |  |
| A20 | Flamme | 192.242.24.149-192.242.24.150 | 192.242.24.149 | 255.255.255.252 |
|  | Himmel |  | 192.242.24.150 |  |

Setelah semuanya sudah selesai tinggal melakukan konfigurasi pada GNS 

<img width="590" alt="Untitled 1" src="https://github.com/aud1tya4dnan/Jarkom-Modul-4-IT18-2023/assets/107627453/fe2e3431-7881-4364-bf25-14d089c58ec0">


### Hasil Konfigurasi

**********AURA********** 

```bash
auto eth0
iface eth0 inet dhcp

#A11 Eisen-Aura
auto eth1
iface eth1 inet static
  address 192.242.24.130
  netmask 255.255.255.252

#A12 Aura-Denken
auto eth2
iface eth2 inet static
  address 192.242.24.133
  netmask 255.255.255.252

#A14 Aura-Frieren
auto eth3
iface eth3 inet static
  address 192.242.24.137
  netmask 255.255.255.252
```

********FREIREN******** 

```bash
#A11 Freiren-Aura
auto eth0
iface eth0 inet static
  address 192.242.24.138
  netmask 255.255.255.252
  gateway 192.242.24.137

#A4 Freiren-Flame
auto eth1
iface eth1 inet static
  address 192.242.24.141
  netmask 255.255.255.252

#A4 Freiren-switch-LakeKorridor
auto eth2
iface eth2 inet static
  address 192.242.24.66
  netmask 255.255.255.224
```

******FLAMME******

```bash
#A11 Flamme-Fieren
auto eth0
iface eth0 inet static
  address 192.242.24.142
  netmask 255.255.255.252
  gateway 192.242.24.141
#A17 flamme-fern
auto eth1
iface eth1 inet static
  address 192.242.24.145
  netmask 255.255.255.252

#A19 flamme-rorhroad
auto eth3
iface eth3 inet static
  address 192.242.12.1
  netmask 255.255.252.0
#A20  flamme-himmel 
auto eth2
iface eth2 inet static
  address 192.242.24.149
  netmask 255.255.255.252
```

**************HIMMEL************** 

```bash
auto eth0
iface eth0 inet static
  address 1192.242.24.150
  netmask 255.255.255.252
  gateway 192.242.24.149

#A21 Himmel-Switch6-SchwerMountains
auto eth1
iface eth1 inet static
  address 192.242.24.97  
  netmask 255.255.255.248
```

**********FERN********** 

```bash
#A11 Flamme-Fern
auto eth0
iface eth0 inet static
  address 192.242.24.146
  netmask 255.255.255.252
  gateway 192.242.24.145

#A18 Fern-Switch4-LaubHills-Switch4-AppetitRegion
auto eth1
iface eth1 inet static
  address 192.242.0.2
  netmask 255.255.248.0
```

************EISEN************ 

```bash
#A11 Eisen-Aura
auto eth0
iface eth0 inet static
  address 192.242.24.129
  netmask 255.255.255.252
  gateway 192.242.24.130

#A4 Eisen-Switch-Stark
auto eth2
iface eth2 inet static
  address 192.242.24.117
  netmask 255.255.255.252

#A10 Eisen-Switch1-Richter-Switch1-Revolte
auto eth3
iface eth3 inet static
  address 192.242.24.105
  netmask 255.255.255.248

#A3 Eisen-lugner 
auto eth4
iface eth4 inet static
  address 192.242.24.113
  netmask 255.255.255.252
#A5 Eisen-linie
auto eth1
iface eth1 inet static
  address 192.242.24.121
  netmask 255.255.255.252
```

************LUGNER************ 

```bash
#A3 Eisen-Lugner
auto eth0
iface eth0 inet static
  address 192.242.24.114
  netmask 255.255.255.252
  gateway 192.242.24.113

#A4 Lugner-TurkRegion
auto eth1
iface eth1 inet static
  address 192.242.8.1
  netmask 255.255.252.0

#A2 Lugner-GrobeForest
auto eth2
iface eth2 inet static
  address 192.242.22.1
  netmask 255.255.255.0
```

************LINIE************ 

```bash
#A3 Eisen-Linie
auto eth0
iface eth0 inet static
  address 192.242.24.122
  netmask 255.255.255.252
  gateway 192.242.24.121

#A6 Linie-Switch-GranzChannel
auto eth2
iface eth2 inet static
  address 192.242.20.1
  netmask 255.255.254.0

#A7 Linie-Lawine 
auto eth1
iface eth1 inet static
  address 192.242.24.125
  netmask 255.255.255.252
```

************LAWINE************

```bash
#A12 Lawine-Linie
auto eth0
iface eth0 inet static
  address 192.242.24.126
  netmask 255.255.255.252
gateway 192.242.24.125

#A8 Lawine-Switch7-Heiter-Switch7-BredtRegion
auto eth1
iface eth1 inet static
  address 192.242.24.1
  netmask 255.255.255.192
```

************HEITER************

```bash
#Heiter-Switch-Lawine
auto eth0
iface eth0 inet static
  address 192.242.24.2
  netmask 255.255.255.192
            gateway 192.242.24.1
            #A9 Heiter-Switch8-Sein-Switch8-RiegelCanyon
auto eth1
iface eth1 inet static
  address 192.242.16.1
            netmask 255.255.252.0
```

**************DENKEN************** 

```bash
#A12 Aura-Denken
auto eth0
iface eth0 inet static
  address 192.242.24.134
  netmask 255.255.255.252
gateway 192.242.24.133

#A13 Denken-Switch2-RoyalCapital-Switch2-WileRegion
auto eth1
iface eth1 inet static
  address 192.242.23.1
  netmask 255.255.255.0
```

**********SCHWERMOUNTAINS**********

```bash
auto eth0
iface eth0 inet static
  address 192.242.24.98
  netmask 255.255.255.248
  gateway 192.242.24.97
```

******************LAUBHILLS******************

```bash
auto eth0
iface eth0 inet static
  address 192.242.0.3
  netmask 255.255.248.0
  gateway 192.242.0.2
```

**************************APPETITREGION**************************

```bash
auto eth0
iface eth0 inet static
  address 192.242.0.1
  netmask 255.255.248.0
  gateway 192.242.0.2
```

********ROHRROAD******** 

```bash
auto eth0
iface eth0 inet static
  address 192.242.12.2
  netmask 255.255.252.0
gateway 192.242.12.1
```

**************************LAKECORRIDOR************************** 

```bash
auto eth0
iface eth0 inet static
  address 192.242.24.67
  netmask 255.255.255.224
gateway 192.242.24.66
```

************************ROYALCAPITAL************************

```bash
auto eth0
iface eth0 inet static
  address 192.242.23.2
  netmask 255.255.255.0
gateway 192.242.23.1
```

********************WILEREGION********************

```bash
auto eth0
iface eth0 inet static
  address 192.242.23.3
  netmask 255.255.255.0
gateway 192.242.23.1
```

**********TURKREGION**********

```bash
auto eth0
iface eth0 inet static
  address 192.242.8.2
  netmask 255.255.252.0
gateway 192.242.8.1
```

**********************GROBEFOREST**********************

```bash
auto eth0
iface eth0 inet static
  address 192.242.22.2
  netmask 255.255.255.0
gateway 192.242.22.1
```

********************GRANZCHANNEL******************** 

```bash
auto eth0
iface eth0 inet static
  address 192.242.20.2
  netmask 255.255.254.0
gateway 192.242.20.1
```

********************BREDREGION********************

```bash
auto eth0
iface eth0 inet static
  address 192.242.24.3
  netmask 255.255.255.192
            gateway 192.242.24.1
```

************************RIEGELCANYON************************

```bash
auto eth0
iface eth0 inet static
  address 192.242.16.3
  netmask 255.255.252.0
  gateway 192.242.16.1
```

**********STARK**********

```bash
auto eth0
iface eth0 inet static
  address 192.242.24.118
  netmask 255.255.255.252
gateway 192.242.24.117
```

****************RICHTER**************** 

```bash
auto eth0
iface eth0 inet static
  address 192.242.24.106
  netmask 255.255.255.248
gateway 192.242.24.105
```

**************REVOLTE**************

```bash
auto eth0
iface eth0 inet static
  address 192.242.24.107
  netmask 255.255.255.248
gateway 192.242.24.105
```

**********SEIN********** 

```bash
auto eth0
iface eth0 inet static
  address 192.242.16.2
  netmask 255.255.252.0
            gateway 192.242.16.1
```

### Routing

**********AURA**********

```bash
A13 -> route add -net 192.242.23.0 netmask 255.255.255.0  gw 192.242.24.134
A4  -> route add -net 192.242.24.116 netmask 255.255.255.252 gw 192.242.24.129
A10  -> route add -net 192.242.24.104 netmask 255.255.255.248  gw 192.242.24.129
A1 (LUGNER-TURKREGION VIA EISEN) -> route add -net  192.242.8.0 netmask 255.255.252.0 gw  192.242.24.129
A2 (LUGNER-GROBEFOREST VIA EISEN) ->  route add -net 192.242.22.0 netmask 255.255.255.0 gw 192.242.24.129
A6 (LINIE-GRANZCHANNEL VIA EISEN) ->  route add -net 192.242.20.0 netmask 255.255.254.0 gw 192.242.24.129
A8 (LAWINE-HEITER-BREDREGION VIA EISEN- LINIE) ->  route add -net 192.242.24.0 netmask 255.255.255.192 gw 192.242.24.129
A9 (Heiter-Switch8-Sein-Switch8-RiegelCanyon VIA EISEN- LINIE-HEITER) ->  route add -net 192.242.16.0 netmask 255.255.252.0 gw 192.242.24.129
A15 (Frieren-switch-lakekorridor VIA FREIREN) ->  route add -net 192.242.24.64 netmask 255.255.255.224 gw 192.242.24.138
A19 (Flamme-Switch5-RohrRoad n VIA FRIEREN-FLAMME) ->  route add -net 192.242.12.0 netmask 255.255.252.0 gw 192.242.24.138
A18 (Fern-Switch4-LaubHills-Switch4-AppetitRegion n VIA FRIEREN-FLAMME-FERN) ->  route add -net 192.242.0.0 netmask 255.255.248.0 gw 192.242.24.138
A21 (Himmel-Switch6-SchwerMountains VIA FRIEREN-FLAMME-HIMMEL) ->  route add -net 192.242.24.96 netmask 255.255.255.248 gw 192.242.24.138
```

**************DENKEN************** 

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.133
```

************EISEN************ 

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.130
A1 (LUGNER-TURKREGION) -> route add -net  192.242.8.0 (LUGNER-TURKREGION) netmask 255.255.252.0 (LUGNER-TURKREGION) gw 192.242.24.114 (IP LUGNER YANG SAMA EISEN)
A1 (LUGNER-TURKREGION) -> route add -net  192.242.8.0 netmask 255.255.252.0 gw 192.242.24.114
A2 (LUGNER-GROBEFOREST) ->  route add -net 192.242.22.0 netmask 255.255.255.0 gw 192.242.24.114
A6 (LINIE-GRANZCHANNEL) ->  route add -net 192.242.20.0 netmask 255.255.254.0 gw 192.242.24.122
A8 (LAWINE-HEITER-BREDREGION VIA EISEN- LINIE) ->  route add -net 192.242.24.0 netmask 255.255.255.192 gw 192.242.24.122
A9 (Heiter-Switch8-Sein-Switch8-RiegelCanyon VIA EISEN- LINIE-HEITER) ->  route add -net 192.242.16.0 netmask 255.255.252.0 gw 192.242.24.122

```

**************LUGNER************** 

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.113
```

************LINIE************ 

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.121
A8 (LAWINE-HEITER-BREDREGION VIA EISEN- LINIE) ->  route add -net 192.242.24.0 netmask 255.255.255.192 gw 192.242.24.126
A9 (Heiter-Switch8-Sein-Switch8-RiegelCanyon VIA EISEN- LINIE-HEITER) ->  route add -net 192.242.16.0 netmask 255.255.252.0 gw 192.242.24.126
```

**************LAWINE************** 

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.125
A9 (Heiter-Switch8-Sein-Switch8-RiegelCanyon VIA EISEN- LINIE-HEITER) ->  route add -net 192.242.16.0 netmask 255.255.252.0 gw 192.242.24.2
```

**************HEITER************** 

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.1
```

****************FREIREN****************

```bash
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.137
A19 (Flamme-Switch5-RohrRoad n VIA FRIEREN-FLAMME) ->  route add -net 192.242.12.0 netmask 255.255.252.0 gw 192.242.24.142
A18 (Fern-Switch4-LaubHills-Switch4-AppetitRegion n VIA FRIEREN-FLAMME-FERN) ->  route add -net 192.242.0.0 netmask 255.255.248.0 gw 192.242.24.142
A21 (Himmel-Switch6-SchwerMountains VIA FRIEREN-FLAMME-HIMMEL) ->  route add -net 192.242.24.96 netmask 255.255.255.248 gw 192.242.24.142
```

************FLAMME************

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.141
A18 (Fern-Switch4-LaubHills-Switch4-AppetitRegion n VIA FRIEREN-FLAMME-FERN) ->  route add -net 192.242.0.0 netmask 255.255.248.0 gw 192.242.24.146
A21 (Himmel-Switch6-SchwerMountains VIA FRIEREN-FLAMME-HIMMEL) ->  route add -net 192.242.24.96 netmask 255.255.255.248 gw 192.242.24.150
```

************HIMMEL************

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.145
```

**********FERN********** 

```bash
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.242.24.145
```
