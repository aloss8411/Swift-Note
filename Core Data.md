Core Data 是一個設計用來儲存資料的框架，背後操作的雖然仍是 SQLite ，但其簡化了資料庫的處理，讓你不用了解 SQL 指令也可以快速的為應用程式建立並使用資料庫。

資料庫顧名思義，是一個用來儲存大量資料的容器，以現實生活來說，最簡單的資料庫可以用一個文件夾來比喻。

例如，一個**文件夾**是用來存放所有學生的資訊，裡頭**每一頁**都代表一名學生的資訊，每一名學生都會有各式各樣的**資訊**，像是姓名、座號、血型或出生年月日等等。

以上例子了解後，我們將它與 Core Data 的內容對比在一起，如下：

現實生活

文件夾

每一頁學生

學生的各個資訊

Core Data

Entity (實體)

每筆資料

Attribute (屬性)

所以假設當我們要為 Core Data 新增一筆資料時，這個步驟為：

1.  首先找出要操作的 Entity (拿出文件夾)。
2.  接著將要新增的一筆資料的各個 attribute 設定好(拿出一張新的紙，將一位新學生的基本資料填上)。
3.  在 Entity 增加這筆資料(為文件夾加入新的一頁，也就是新增這位學生的資訊)。
4.  儲存這個增加資料的動作(文件整理完畢，將文件夾關上)。


研究上CoreData可分為三層級
# Managed Object Model：
用來讀取與呈現Core Data Model內的物件結構，Core Data Model是建立CoreData後出現的xcdatamodeld檔案。

在Core Data Model內可以建立實體(Entity)、屬性(Attributes)與資料關聯性(Relationship)等設定。

# Managed Object Context：
可以在這裡對Managed Object(資料)做儲存、新增、刪除等動作，在使用CoreData存取之前需要使用Managed Object Context，這功能就像一個暫存記憶體(scratch pad memory)用來存取著Managed Object，暫存著一個或多個Managed Object，當接收到儲存指令後才會將Managed Object存取至Persistent Store。

# Persistent Store Coordinator：
是一個中介的角色，處於Managed Object Model與Persistent Store之間，負責處理資料的讀取與寫入。Persistent Store是實際將資料儲存的地方，是iOS內建的SQLite資料庫。目前自己所知道的Persistent Store儲存方式有四種，分別為：



# 實際處理

－ NSpersistentContainer中的saveContext


如何部分搜尋CoreData裡面的資料
https://nspredicate.xyz/#contains-certain-string