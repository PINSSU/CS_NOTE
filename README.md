# CS_NOTE

# linux背景知識
版本分為：

1.開發中版本範例(主次版本為奇數)：2.5.x

2.穩定版本範例(主次版本為偶數)：2.6.x

開發商有提供『線上升級』機制，透過此機制， 原版光碟就只有第一次安裝時需要用到，其他時候只要有網路，就能夠取得原開發商所提供的任何軟體。

# 檔案命名
區分英文字元大小寫，通常以小寫為主

檔名長度至多256個字元，可包括字母、數字、.(點)、_、-

不可包括?、*、空格、$、&、/

# linux指令
* cd-變換目錄

* pwd-顯示目前的目錄

* ls-顯示目錄的的所有內容

* cat-查看檔案內容

* rmdir-刪除一個裡面是空的空目錄

* mkdir-建立一個新目錄

# 絕對路徑與相對路徑
* 絕對路徑：

路徑的寫法『一定由根目錄 / 寫起』，例如： /usr/share/doc

* 相對路徑：

路徑的寫法『不是由 / 寫起』，例如由 /usr/share/doc 要到 /usr/share/man 底下時

寫成： 『cd ../man』，相對路徑意指『相對於目前工作目錄的路徑』

# 編輯文檔
* nano

Ctrl+X：離開

Ctrl+C：顯示游標所在

Ctrl+W：查詢命令

Ctrl+O：寫入

* vi/vim

一般模式：

可是使用上下左右標移動、刪除字元以及複製貼上檔案

編輯模式：

編輯文字，i鍵進入編輯模式，ESC即退出編輯模式

:w 將編輯的資料寫入硬碟檔案中

:w! 若檔案屬性為『只讀』時，強制寫入該檔案(!為強制)

:q 離開

:wq 儲存後離開

:w[filename] 將編輯的資料儲存成另一個檔案(類似另存新檔)

:r[filename] 在編輯的資料中，讀入另一個檔案的資料

set nu 顯示行號，設定後會在每一列的自首顯示該列的行號

# 使用者與群組
* 身份分類

user (owner)

group

others

* 群組的主要用意

將帳號歸類，有助於類似專案開發

每個使用者均可加入多個群組

* 系統管理員：root

* 一般帳號：

系統帳號 (用於系統帳號的工作)

一般使用者帳號 (用於一般使用者登入用)

# 檔案語法
 /.(根目錄)：所有的檔案皆從根目錄開始，只有root使用者具該目錄的許可權

/root：此目錄為系統管理員，也稱作超級許可權者的使用者主目錄

/bin：存著經常使用的指令

/boot：系統啟動時必須讀取的檔案，包括系統核心、連線檔案以及映象檔案

/dev：存放周邊設備代號的檔案

/etc：放置與系統設定、管理相關的檔案

/home：存放普通使用者的主目錄，在linux中每個使用者都有一個自己的目錄，一般該目錄名是以使用者的帳號命名的

/media：可用來做為光碟、軟碟片、隨身碟與其他分割區的自動掛載點

/tmp：供全部使用者暫時放罝檔案的目錄

/usr：為非常重要的目錄，使用者的很多應用程式和檔案都放在此目錄下，類似windows下的program files目錄

/var：系統執行時，內容經常變動的資料或暫存檔(1og file)，都會放置在這個目錄裡

# 壓縮檔案
* gzip

壓縮：

gzip FileName

解壓縮：

gunzip FileName.gz

gzip -d FileName.gz

* xz

壓縮：

xz -z FileName

解壓縮：

xz -d FileName.xz

* tar.gz

壓縮：

tar -zcvf FileName.tar.gz DirName

解壓縮：

tar -zxvf FileName.tar.gz

# 網路相關
* route

add : 新增一條路由規則

del : 刪除一條路由規則

-net : 目的地址是一個網路

-host : 目的地址是一個主機

target : 目的網路或主機

netmask : 目的地址的網路掩碼

gw : 路由資料包通過的閘道器

dev : 為路由指定的網路介面

* ping

常用網路檢測工具，可籍由發送ICMP ECHO REQUEST封包，檢查自己與特定設備之間的網路是否暢通，並同時測量網路連線的來回通訊延選時間(round-trip delay time)

-n：參數指定封包數

EX：ping -n 10 blog.gtwang.org

-t：持續監看網路是否正常

EX：ping -t blog.gtwang.org

-4/-6：IPv4/IPv6-c：指定Ping次數

EX：ping -c 4 blog.gtwang.org

-s：指定發送的數據字結數

EX：ping -s 1024 facebook.com

-i：指定收發資訊間隔時間

EX：ping -i 0.4 facebook.com

* 影響網路速度的因素

延遲(Latency)：封包從來源端至目的端中間所花的時間

頻寬(Bandwidth)：傳輸媒介的最大吞吐量

* netstart

查看端口是否被占用：netstat -a|grep 3306

查看數據包統計信息：netstat -s

查看路由信息：netstat -r
