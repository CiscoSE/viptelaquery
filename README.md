# viptelaquery

## Description
This is a very basic application to query the vManage application within a Cisco SD-WAN (Viptela) Infrastructure. The code supports several basic functions to login to the vManage and retrieve the data in different formats.

## Function Descriptions
This python script implemnents four basic functions that are described below:
* initalize_connection - Initializes a connection to the vManage server
* get_inventory - Get an inventory dictionary that correlates the system-ip with the hostname
* get_statistic - Return the interface statistics for each interface in each device
* get_tunnel_statistic - For a given vEdge, return the statistics on all the tunnels that are defined on that device


## Example Output
```
Viptela vManage Engine Starting...

Viptela Configuration:
vManage Server Address: 198.18.1.10:8443
vManage Username: admin
Retrieving the inventory data from the vManage at 198.18.1.10:8443

System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.3.0.1         BR1-VEDGE1            17.1.1      52c7911f-c5b0-45df-b826-3155809a2a1a


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
      ge0/1         0                577748         1501823
      ge0/2         0                446444          872385
      ge0/3         0                128260          129811
      system        0                     0               0
      ge0/0         10              1557458          608160
      loopback0     20                    0               0
      loopback1     30                    0               0
      eth0          512                1394           20150
                                 ----------      ----------
                    Total           2711319         3132347


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.3.0.2         BR1-VEDGE2            17.1.1      0a4a4c78-35a8-4c1c-bbd2-e02516606fd7


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
      ge0/1         0                623955         1034484
      ge0/2         0                870751          448094
      ge0/3         0                128153          129907
      system        0                     0               0
      ge0/0         10                  260          727717
      eth0          512                1393           20137
                                 ----------      ----------
                    Total           1624525         2360349


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.4.0.1         BR2-VEDGE1            17.1.1      ddd801b2-8cbe-4394-abd1-3b71e39886e3
An Error Occured processing the data
System IP 10.4.0.1 is not connected to vmanage


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.1.0.1         DC1-VEDGE1            17.1.1      ebdc8bd9-17e5-4eb3-a5e0-f438403a83de


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
      ge0/1         0                261270          216530
      ge0/2         0                343318          369537
      system        0                     0               0
      ge0/0         10               281878          331641
      eth0          512                1396           20351
                                 ----------      ----------
                    Total            887871          938093


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.1.0.2         DC1-VEDGE2            17.1.1      f21dbb35-30b3-47f4-93bb-d2b2fe092d35


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
      ge0/1         0               1272245          201370
      ge0/2         0                654092          186249
      system        0                     0               0
      ge0/0         10                82600         1653052
      eth0          512                1327           20323
                                 ----------      ----------
                    Total           2010273         2061015


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.2.0.1         DC2-VEDGE1            17.1.1      9e785ad7-558a-40c6-b0c0-fcc96e6d04ca


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
      ge0/1         0                127632          325383
      ge0/2         0                167111          179538
      system        0                     0               0
      ge0/0         10               200249            7847
      eth0          512                1329           20299
                                 ----------      ----------
                    Total            496329          533079


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.2.0.2         DC2-VEDGE2            17.1.1      b3265c5c-3db6-4d25-9d3b-1f416b89adb0


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
      ge0/1         0                164052          199879
      ge0/2         0                129757          138686
      system        0                     0               0
      ge0/0         10                34655            7944
      eth0          512                1396           20267
                                 ----------      ----------
                    Total            329868          366781


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
11.11.11.11      vbond                 17.1.1      abd5e9d7-9dee-4d00-98b5-fdc71de6ea63


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
                                 ----------      ----------
                    Total                 0               0


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
10.10.10.10      vmanage               17.1.1      5271ea7c-edb1-420b-be9a-4d25756785bd


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
                                 ----------      ----------
                    Total                 0               0


System IP        Hostname              Version     UUID
---------        --------              -------     ------------------------------------
12.12.12.12      vsmart                17.1.1      10a98779-95f0-4383-871c-195d25bd9c74


      ifName        vpn-id       tx-packets      rx-packets
      ------        ------       ----------      ----------
                                 ----------      ----------
                    Total                 0               0


Returning the tunnel statistics for device: 10.3.0.2

     Tunnel                   Color           RX Pkts    TX Pkts     RX Bytes     TX Bytes
     ------                   -----           -------    -------     --------     --------
BR1-VEDGE2->DC1-VEDGE1     mpls                 27393      27393     29693984     26626024
BR1-VEDGE2->DC1-VEDGE2     mpls                 27381      27381     29680976     26614360
BR1-VEDGE2->DC2-VEDGE1     mpls                 27052      27193     29324368     26435544
BR1-VEDGE2->DC2-VEDGE2     mpls                 27322      27322     29617048     26556984
BR1-VEDGE2->DC1-VEDGE1     biz-internet         27337      27337     36631552     33569864
BR1-VEDGE2->DC1-VEDGE2     biz-internet         27323      27323     36612792     33552672
BR1-VEDGE2->DC2-VEDGE1     biz-internet         27333      27333     36626192     33564952
BR1-VEDGE2->DC2-VEDGE2     biz-internet         27322      27322     36611480     33551416
                                                                    ---------    ---------
                                               Totals:              264798392    240471816
```

