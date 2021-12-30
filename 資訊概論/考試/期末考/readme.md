# 第二章 WWW
## URL (see p30-p31)
- uniform resource locator，全球資源定位器
- 用途 ==>
- https://my.ksu.edu.tw/file/web/CHT/DAAACIS/b38de400-d78b-46c8-a922-993cfeffe5f4.pdf
- https ==>通訊協定  Hypertext Transfer Protocol Secure ==> TLS（Transport Layer Security）
- ksu.edu.tw ==>網域
- my.ksu.edu.tw ==>伺服器位址
- 路徑名稱
- 檔案名稱

## http

## https  ==> SSL TLS

- xampp  https  ==>https://vector.cool/xampp-apache-https-in-localhost/


## Ip address
- 用途 ==>
- 組成 ==> 
- 32 bits
- 表達方式 ==> dot-decimal notation
- 120.113.22.33
- 0.0.0.0- 255.255.255.255

## domain name ==> 整個企業
- google.com網域
- ns1.google.com ==> 某一個伺服器
- ns2.google.com ==> 某一個伺服器
- www.google.com ==> 某一個伺服器
- TLD ==> Top level domain
- com ==>  
- edu ==>
- gov ==> 

## web

- web server ==> apache
- web application ==> 你寫的程式

## 資訊`素養`（information `literacy`） 
```
現代人如何能有效率的找到、評估、使用和傳達線上資訊
能做到下列這些事：
  參考多種資訊來源，包括 Internet、線上圖書館和媒體網站
  選擇正確的工具找到需要的資訊
  體認到並非所有資訊都生而平等
  評估資訊是否會使人誤解、偏頗或已經過時
  駕馭資訊成為讓自己成為具備知識的決策者
```

## SEO(Search engine optimization)

## CARS
```
CARS（credibility, accuracy, reasonableness, support）查核清單（checklist）
可信度（credibility）：找出作者，了解他們的身分
正確性（accuracy）：確認它的事實來源和主張，了解它是否有特定立場或偏見
合理性（reasonableness）：要考慮線上來源的內容是否公正且合乎情理
支持度（support）：找找看聲譽良好的來源或機構
```
## 
## Creative Commons（CC）
- 是個`非營利`機構
- 它協助讓`內容創作者`能保有自己創作素材的`版權`
- 同時還能讓`他人使用、複製或散布`他們的作品

# 第三章 計算機硬體
- 范紐曼型架構（[Von Neumann architecture](https://en.wikipedia.org/wiki/Von_Neumann_architecture)），也稱馮·紐曼模型（Von Neumann model）或普林斯頓架構（Princeton architecture）
  - A processing unit that contains an arithmetic logic unit and processor registers
  - A control unit that contains an `instruction register` and `program counter`
  - Memory that stores data and instructions
  - External mass storage
  - Input and output mechanisms
  - 處理器快取（processor cache）就在處理器隔壁，所以處理器能很方便且很快地存取快取內的資料。
  - 控制單元（control unit）負責管理處理器內指令的流向
  - 算術邏輯單元（arithmetic logic unit, ALU）負責執行算術運算。
- stored-program ==> `instructions(指令)`
  -  instructions(機器指令|第一代程式) ==> 組合語言(機器指令翻成人看得懂的程式語言|第二代程式)  ==> low-level
  -  statement| program ==> C (高階語言|第三代程式) ==> high-level
  -  第4代程式 ==> SQL
- 機器週期（machine cycle）或指令週期（instruction cycle）
  - 當 CPU 在執行每個指令時，會經過一組 4 個步驟 ==> 機器週期（machine cycle）或指令週期（instruction cycle）
  - 機器週期是由擷取（fetch）、解碼（decode）、執行（execute）和儲存（store） 4 個步驟所組成。
  - 擷取和解碼指令是由控制單元（control unit）負責
  - 執行和儲存指令則是由 ALU 負責進行。


- 記憶體階層 (Memory hierarchy)
  - 隨機存取記憶體（random access memory, RAM）  vs  唯讀記憶體（read-only memory, ROM）
  - 虛擬記憶體（virtual memory）
  - 置換檔（swap file）分頁檔（paging file）
- 唯讀記憶體（read-only memory, ROM）
  - 永久安裝在電腦，而且是附著在主機板上
  - ROM 晶片內含 BIOS，它負責告訴電腦如何啟動。
  - BIOS 也會進行所謂的開機自我檢測（power-on self test, POST），這道程序會測試電腦的全部元件是否能正常運作
  - 電腦廠商會時常更新 ROM 晶片上的指令，也稱作`韌體（firmware）`
- 處理器的`時脈速度（clock speed）`
  - 測量它能以多快的速度執行指令。
  - 時脈速度可以用 MHz（megahertz，百萬赫茲）或 GHz（gigahertz，十億赫茲）為單位。
  - 百萬赫茲是每秒百萬次時脈週期，而十億赫茲則是每秒十億次時脈週期。
- 一個`時脈週期（cycle）`
  - 是測量處理程序（process）的最小時間單位。
  - CPU 的效率則是以每個時脈週期能執行的指令個數（instructions per cycle, IPC）為單位。
- BUS
  - 匯流排的速度和寬度是影響電腦效能的另一個重要因素。
  - 匯流排是一種能讓 CPU 與電腦內部或外接的各種裝置相互通訊的電子通道。
  - 匯流排寬度（bus width）會決定資料傳輸的速度，它也被稱為字組大小（word size）。
- 不斷電電源供應器（uninterruptable power supply, UPS） 
- 突波抑制器（surge suppressor） 


# 第九章 網頁程式設計
- 客戶端網頁程式開發(Client-side web programming)
  - [HTML 範例學習](https://www.w3schools.com/html/html_examples.asp)
  - [CSS 範例學習](https://www.w3schools.com/css/css_examples.asp)
  - [JavaScript 範例學習](https://www.w3schools.com/js/js_examples.asp)
- 伺服端網頁程式開發(server-side web programming)
  - [PHP 範例學習](https://www.w3schools.com/php/php_examples.asp)
  - JSP
  - ASP.NET

- HTML ==> 
  - `內容`
  - 最新版本
  - `標籤(tag)` ==> 用來描述網頁上內容的資訊
  - 範例1:`超連結`標籤(tag) ==>
  - 範例2:`youtube`標籤(tag) ==>

- CSS
  - 外觀 ==> 彩妝師 
  - 用來指定網頁上的內容在瀏覽器中將會如何顯示 
  - 階層式樣式表（Cascading Style Sheets，CSS；又稱串樣式列表、級聯樣式表、串接樣式表、階層式樣式表）
  - 用途:一種用來為結構化文件（如HTML文件或XML應用）添加樣式（字型、間距和顏色等）的電腦語言
  - 用途:使用 CSS 來指定色彩、位置、對齊方式、字型、背景圖片等屬性
  - 由W3C定義和維護
- Javascript
  - 動態
  - 行為 ==> mouseover 
  - 用途 ==> 前端驗證
  - 可以開發`伺服端網頁程式開發(node.js)`
- 靜態（static）網站 vs 動態（dynamic）網站
  - 靜態（static）網站提供的是不常變動的基本資訊，通常選擇用 HTML+CSS 語言來編寫網頁程式碼
  - 動態（dynamic）網站經常是使用伺服端腳本語言（server-side scripting language）及Javascript 來製作。比較複雜的網站是動態的
- RWD
  - 自適應網站設計（responsive web design）
  - 根據顯示螢幕的尺寸自動調整內容的版面
  - 著名套件:  [bootstrap](https://getbootstrap.com/)
- 專案 ==> [google site 協作平台](https://web-design.vip/google-sites.html)
- CMS
  - 內容管理系統（content management system, CMS）
  - 可能有多位投稿者（contributor）的複雜網站
  - WORDPRESS是開放原始碼軟體
  - WORDPRESS專案 ==> [WORDPRESS架站](https://web-design.vip/6-step-wordpress-web-design.html)
  - [WordPress.com：又快又安全的WordPress 託管服務](https://wordpress.com/zh-tw/)
    - https://happyhackinghigh.wordpress.com/
    ![管理介面]()
    -  
- IDE
  - 整合式開發環境（Integrated Development Environment, IDE）
  - 結合進階的程式碼編輯器工具、偵錯工具、檔案管理工具和發布工具，能簡化開發網站和應用程式的程序
  - 大多數 IDE 含有程式碼編輯器（code editor）
  - 將網站的檔案和資料夾，儲存在所謂的專案（project）的資料夾或目錄中
  - 範例: [Visual Studio Code - Code Editing. Redefined](https://code.visualstudio.com/)
 
- 網站分析（website analytics）
  - 協助網站擁有者了解人們是如何使用自己的網站
    - 訪客是哪些人
    - 來自哪裡
    - 與網站的互動方式
  - 範例: Google Analytics
- XML
  - XML（Extensible Markup Language 的縮寫，可延伸標記語言） 
  - 是用來分類資料並在應用程式之間分享它  ==> json

## 課本網站開發主題
- 9-4 編寫網站程式碼與發布網站
```
編寫網站的程式碼
新增網頁標題、內容標題和斷行設定
新增影像
新增連結
新增無序列表和有序列表
在網頁上加入多媒體內容
檢查你的 HTML 程式碼的有效性
將製作完成的網站發布到 Internet
用 CSS 來修飾網頁的外觀
用 JavaScript 操控網頁的行為
```
