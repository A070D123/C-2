
# arp


C:\Users\KSUIE>arp /?

顯示和修改位址解析通訊協定 (ARP) 使用的 IP 對

實際位址轉譯表格。

ARP -s inet_addr eth_addr [if_addr]

ARP -d inet_addr [if_addr]

ARP -a [inet_addr] [-N if_addr] [-v]

  -a            質詢目前的通訊協定資料來顯示目前的
  
                ARP 項目。如果指定 inet_addr，只會顯示指定電腦的
                
                IP 及實體位址。如果有多個網路介面使用 ARP，便會顯示每個 ARP
                
                表格的項目。
                
  -g            與 -a 相同。
  
  -v            以詳細資訊模式顯示目前的 ARP 項目。將會顯示
  
                所有無效項目和回路介面上的項目。
                
  inet_addr     指定網際網路位址。
  
  -N if_addr    顯示 if_addr 指定之網路介面的 ARP
  
                項目。
                
  -d            刪除 inet_addr 指定的主機。使用萬用字元 * 取代 inet_addr
  
                可刪除所有主機。
                
  -s            新增主機並將網際網路位址 inet_addr 與實體位址
  
                eth_addr 相關聯。實體位址是
                
                6 個以連字號分隔的十六進位位元組。該項目
                
                永久不變。
                
  eth_addr      指定實體位址。
  
  if_addr       如果存在，這會指定介面的網際網路位址，
  
                應修改此介面的位址轉譯表格。
                
                如果不存在，將會使用第一個適用的介面。
                
範例:

  > arp -s 157.55.85.212   00-aa-00-62-c6-09  .... 新增靜態項目。
  
  > arp -a                                    .... 顯示 ARP 表格。
  
  # arp -a
  
  C:\Users\KSUIE>arp -a

介面: 192.168.56.1 --- 0x4

  網際網路網址          實體位址               類型
  
  192.168.56.255        ff-ff-ff-ff-ff-ff     靜態
  
  224.0.0.3             01-00-5e-00-00-03     靜態
  
  224.0.0.22            01-00-5e-00-00-16     靜態
  
  224.0.0.251           01-00-5e-00-00-fb     靜態
  
  224.0.0.252           01-00-5e-00-00-fc     靜態
  
  239.255.255.250       01-00-5e-7f-ff-fa     靜態

介面: 172.20.155.223 --- 0x8

  網際網路網址          實體位址               類型
  
  172.20.155.19         88-d7-f6-53-82-e6     動態
  
  172.20.155.44         8c-16-45-56-0b-b1     動態
  
  172.20.155.140        88-d7-f6-53-24-d8     動態
  
  172.20.155.167        88-d7-f6-53-83-6f     動態
  
  172.20.155.226        40-16-7e-44-f7-f7     動態
  
  172.20.155.254        00-14-1b-72-a8-00     動態
  
  172.20.155.255        ff-ff-ff-ff-ff-ff     靜態
  
  224.0.0.3             01-00-5e-00-00-03     靜態
  
  224.0.0.22            01-00-5e-00-00-16     靜態
  
  224.0.0.251           01-00-5e-00-00-fb     靜態
  
  224.0.0.252           01-00-5e-00-00-fc     靜態
  
  239.255.255.250       01-00-5e-7f-ff-fa     靜態
  
  255.255.255.255       ff-ff-ff-ff-ff-ff     靜態

介面: 192.168.173.2 --- 0x9

  網際網路網址          實體位址               類型
  
  192.168.173.255       ff-ff-ff-ff-ff-ff     靜態
  
  224.0.0.3             01-00-5e-00-00-03     靜態
  
  224.0.0.22            01-00-5e-00-00-16     靜態
  
  224.0.0.251           01-00-5e-00-00-fb     靜態
  
  224.0.0.252           01-00-5e-00-00-fc     靜態
  
  239.255.255.250       01-00-5e-7f-ff-fa     靜態

  # ipconfig /?
```
C:\Users\KSUIE>ipconfig /?

使用方式:
        ipconfig [/allcompartments] [/? | /all |
                                 /renew [adapter] | /release [adapter] |
                                 /renew6 [adapter] | /release6 [adapter] |
                                 /flushdns | /displaydns | /registerdns |
                                 /showclassid adapter |
                                 /setclassid adapter [classid] |
                                 /showclassid6 adapter |
                                 /setclassid6 adapter [classid] ]


其中
    adapter             連線名稱
                       (允許使用萬用字元 * 與 ?，請見範例)

    選項:
       /?               顯示此說明訊息。
       /all             顯示完整設定資訊。
       /release         釋放指定介面卡的 IPv4 位址。
       /release6        釋放指定介面卡的 IPv6 位址。
       /renew           更新指定介面卡的 IPv4 位址。
       /renew6          更新指定介面卡的 IPv6 位址。
       /flushdns        清除 DNS 解析快取。
       /registerdns     重新整理所有 DHCP 租用並重新登錄 DNS 名稱。
       /displaydns      顯示 DNS 解析快取的內容。
       /showclassid     顯示介面卡所有允許的 DHCP 類別識別碼。
       /setclassid      修改 DHCP 類別識別碼。
       /showclassid6    顯示介面卡允許的所有 IPv6 DHCP 類別識別碼。
       /setclassid6     修改 IPv6 DHCP 類別識別碼。

預設是僅顯示每個繫結到 TCP/IP 之介面卡的 IP 位址、子網路遮罩及預設閘道。

對於 Release 與 Renew，如果沒有指定介面卡名稱，則會釋放或更新所有繫結到
TCP/IP 介面卡的 IP 位址租用。

對於 Setclassid 與 Setclassid6，如果沒有指定 ClassId，則將移除 ClassId。

範例:
    > ipconfig                       ... 顯示資訊
    > ipconfig /all                  ... 顯示詳細資訊
    > ipconfig /renew                ... 更新所有介面卡
    > ipconfig /renew EL*            ... 更新所有名稱開頭為 EL 的連線
    > ipconfig /release *Con*        ... 釋放所有符合的連線，
                                         例如 "Wired Ethernet Connection 1" 或
                                              "Wired Ethernet Connection 2"
    > ipconfig /allcompartments      ... 顯示所有區間的相關資訊
    > ipconfig /allcompartments /all ... 顯示所有區間的詳細資訊
```