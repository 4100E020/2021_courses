# [Wireshark](https://www.wireshark.org/)
- [termshark](https://github.com/gcla/termshark)
## 封包分析




### [capture filter](https://wiki.wireshark.org/CaptureFilters)

### [display filter](https://wiki.wireshark.org/DisplayFilters)

### Follow TCP/UDP/SSL stream 

## DNS

### TLDs (Top-Level Domains)
- 由 [Root Domain (根網域)](https://blog.dcplus.com.tw/marketing-knowledge/trend/26368) 管理
#### [gTLD (Generic TLDs, 一般最上層領域名稱)](https://blog.twnic.tw/2021/06/29/19122/)
- 涵蓋 .com、. net、. org等。
- 每個 gTLD都由專屬的註冊管理機構負責維護位址清單，再透過受理註冊機構銷售網域名稱。

|名稱|代表意義|
|---|-------|
|com|公司、行號、企業|
|org|組織、機構|
|edu|教育單位|
|gov|政府單位|
|net|網路、通訊|
|mil|軍事單位|

#### [ccTLD (Country code TLDs, 國碼最上層領域名稱)](https://blog.twnic.tw/2021/05/27/18788/)
- 依照ISO 3166國際標準「國家名稱及其細分代表代碼」當中定義的多組2字元字母，來代表特定的國家或獨立的經濟體。

|名稱|代表意義|
|---|-------|
|tw|台灣(Taiwan)|
|uk|英國(United Kingdom)|
|in|印度(India)|

### Message Format(沒有固定欄位)
![](https://i.imgur.com/6xB9RQa.png)

#### 識別碼(Identification)
- 
#### 旗標(Flags)
- 16 位元旗標示用來描述此 DNS 訊息封包的功能
- QR（Question/Response）
- OP-code（Operating Code）A
#### 權威計數(Number of questions)

#### 答案 RR 計數(Number of answer RRs)

#### Number of authority RRs

#### Number od additional RRs

#### Questions

#### Authority

#### Additional information

### Resource Record(RR)
|RR 類型|意義|說明|
|------|---|----|
|A(address)|查詢 IPV4 位址紀錄|將 Domain Name 對映到一個主機的 IPv4 的位址。|
|AAAA|查詢 IPv6 位址紀錄|將 Domain Name 對映到一個主機的 IPv6 位址。|
|CNAME(canonical name)|定義主機正規名稱的Domain Name|可為同一部主機設定許多Domain Name。|
|MX|SMTP 郵件交換器|設定區域中擔任郵件伺服器的主機，所有要送往那部機器的 mail 都要經過 mail exchanger 轉送。而數字則是該主機郵件傳遞時的優先次序，此值越低表示有越高的郵件處理優先權。|
|NAPTR(Name Authority Pointer)|---|RFC 3403定義，它提供了正規表示式方式去對映一個域名。NAPTR記錄非常著名的一個應用是用於ENUM查詢。|
|PTR(pointer)|IP位址轉換成網域名稱|定義某個 IP 對應的 domain name，即將 IP 位址轉換成主機的FQDN。|
|NS|定義有管轄權的名稱伺服器|用來指定操作的DNS伺服器主機名稱，需注意的是不可以IP位址表示。|
|SRV(Service Record)|服務位置記錄|用來查詢指定服務的地址，SRV中除了記錄伺服器的地址，還記錄了服務的埠，並且可以設定每個服務地址的優先順序和權重。|
|SOA|查詢管理 Domain Name 的伺服器管理資訊|----|

### Reference
- [圖片來源](https://electronicspost.com/dns-messages/)
- [[整理] DNS and DNS packet format in wireshark](https://littlechocho.pixnet.net/blog/post/186904533)
- [DNS 資源紀錄(Resource Record)介紹](http://dns-learning.twnic.net.tw/bind/intro6.html)
- [DNS 運作原理](https://medium.com/後端新手村/域名系統-dns-101-7c9fc6a1b8e6)
- [DNS 伺服器_鳥哥](http://linux.vbird.org/linux_server/0350dns.php)

## UDP
### Message Format
![](https://i.imgur.com/jq3qzjw.png)
 
#### 來源埠口(Source Port)
- 發送端之傳輸埠口。
 
#### 目的埠口(Destination Port)
- 接收端之傳輸埠口。
 
#### 長度(Length)
- 該封包所承載資料（Data）的長度。
 
#### 檢查集(Checksum)
- 該封包之錯誤檢查的檢查集。
- 虛擬標頭(Pseudo Header)
    |類型|說明|
    |---|----|
    |IP Source Address|（4 Bytes）IP 標頭之來源 IP 位址。|
    |IP Destination Address|（4 Bytes）IP 標頭之目的 IP 位址。|
    |Protocol|（1 Byte）IP 標頭之協定號碼欄位。|
    |Length|（2 Bytes）UDP 標頭之長度欄位。|
    |Padding|（1 Bytes）補滿虛擬標頭成為偶數位元組長度，以方便計算 Checksum。|
 
### Reference
- [圖片來源](http://www.tcpipguide.com/free/t_UDPMessageFormat.htm)
- [TCP/IP 協定與 Internet 網路：第七章 傳輸層協定](http://www.tsnien.idv.tw/Internet_WebBook/chap7/7-5%20UDP%20%E9%80%9A%E8%A8%8A%E5%8D%94%E5%AE%9A.html)

## TCP
### Message Format
![](https://www.gatevidyalay.com/wp-content/uploads/2018/09/TCP-Header-Format.png)

![](https://i.imgur.com/WWodyag.png)

#### 來源埠口(Source Port)
#### 目的埠號(Destination Port)
### Reference
- [圖片來源](https://www.gatevidyalay.com/transmission-control-protocol-tcp-header/)
- [圖片來源](https://notfalse.net/26/tcp-seq)

## IP
### IP Message Format
![](https://i.imgur.com/nU2haZB.png)

#### 版本（Version）
- 4 位元。表示 IP 封包的 IP 版本。

#### 標頭長度（Header Length, HL）
- 4 位元。表示本 IP 封包標頭的長度（位元組表示）。範圍為 5 ~ 15，預設值為 5。

#### 服務型態（Type of Service, TOS）
- 8 位元。其內容為 "PPPDTRUU"，PPP 表示本 IP 封包的優先權（Precedence）；D = 0 表示一般延遲（Delay），D = 1 表示低延遲；T = 0 為一般傳送量（Throughput），T = 1 為高傳送量；R = 0 為一般可靠度，R = 1 為高可靠度（Reliability）；UU 保留未用。

#### 總長度（Total Length）
- 16 位元。是指該封包的總長度，包括封包標頭及資料的長度，範圍由 576 ~ 65535 位元組。

#### 辨識碼（Identification）
- 8 位元。表示資料分割（fragmentation）的識別編號。同一筆資料如被分割成若干個區段，每段給予相同的辨識碼，接收端再依辨識碼組合回原來資料封包。

#### 旗標（Flags）
- 3 位元。其格式為 "0DM"。D = 0 表示可以分段，D = 1 為不可分段（Don’t fragment）；M = 0 表示最後分段，M = 1 為不是最後分段（More fragment）。

#### 分段偏移（Fragment Offset）
- 13 位元。表示目前的分段在原始的資料中所在的位址。原始分段允許有 8192 個分段，以每 8 個位元為一個基本偏移量，所以最大容許 65536 位元資料，此值和總長度一樣。因此範圍為 0 ~ 8191，預設值為 0。

#### 存活時間（Time to Live, TTL）
- 8 位元。表示該封包在網路上的存活時間，封包每經過一個路由器（或網路閘門），該值就被減一。如路由器發現某封包的 TTL = 0，便將該資料片丟棄而不轉送。範圍 0 ~ 255。

#### 協定（Protocol）
- 8 位元。表示該 IP 封包所承載通訊協定的協定號碼。在 TCP/IP 協定中，任何通訊協定（如IP、ICMP、TCP、UDP等等）的資料在傳送中都被包裝成 IP 封包，而以 IP 通訊協定發送。所以，在IP 封包裡必須有協定號碼欄位，來表示目前所承載之資料是屬於哪一個通訊協定（IP、ICMP、TCP 等等）。一些較常用著名（well-known）的協定號碼如表 5-1 所示。

#### 標頭檢查集（Header Checksum）
- 16 位元。做標頭錯誤檢查用。

#### 來源位址（Source IP Address）
- 32 位元。發送此 IP 封包的來源位址。

#### 目的位址（Destination IP Address）
- 32 位元。目的主機之位址。

#### 選項欄位（Options(Variable length)）
- 可變長度。提供多種選擇性服務。目前已定義使用有下列：
    - 安全處理機制：有關資料加密與認證。
    - 路由紀錄：當 IP 封包經過路由器時，讓該路由器登錄其 IP 位址。當封包到達目的地時，可追蹤它所經過的路徑。
    - 時間戳記：當 IP 封包經過路由器時，讓路由器登錄其 IP 位址和時間。
    - 寬鬆來源路由（Loose Source Routing）：記錄該封包所必須經由之路徑，為一 IP 位址的序列表。
    - 嚴格來源路由（Strict Source Routing）：如同寬鬆來源路由，但嚴格規定祇能依照 IP 序列表傳送該封包。

#### 填補欄位（Padding）
- IP 資料片的標頭一定是 32 位元的整數倍，當 Options 欄位不足 32 位元整數倍時由 Padding 欄位補足。

### Reference
- [IPv4 Packet Format](https://support.huawei.com/enterprise/en/doc/EDOC1000178017/dd76ea1f/ipv4-packet-format)
