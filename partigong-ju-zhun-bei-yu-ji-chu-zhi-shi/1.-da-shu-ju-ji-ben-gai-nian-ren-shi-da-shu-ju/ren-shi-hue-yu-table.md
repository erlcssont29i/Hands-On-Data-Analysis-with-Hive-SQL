# 認識Hue與Table

由於大數據框架很多，為了解決某個問題，一般來說會用到多個框架，但是每個框架又都有自己的web UI監控界面，對應著不同的端口。這個時候有一個統一的web UI界面去管理各個大數據常用框架就非常方便。

Hue是一個開源的Apache Hadoop UI系統，通過Hue我們可以在瀏覽器端的Web控制台上與Hadoop進行進行交互來處理數據。

在Query Editors，左側可查看數據庫、數據表

1.  **database 數據庫**

    相當於關聯式資料庫裏的命名空間（namespace），它的作用是將用戶和資料庫的應用隔離到不同的資料庫或模式中，可以想像為是一個文件櫃，這個櫃子是一個存放數據的物理位置，不管數據是什麼，也不管數據如何組織的。
2.  **table 表**

    表名要唯一，在相同的數據庫中不能使用兩次同樣的表名，但在不同庫是可以使用相同的表名
3.  **column 字段**

    所有表都是由一個或是多個column所組成，每個column都有相應的**數據類型**
4.  **row 表中的一條紀錄**

    每一條紀錄中的唯一標示稱為主鍵(Primary key )，能夠唯一代表表中的每一行，**但並不是總是需要主鍵**

****

表結構表示一張表由**哪些字段及字段的數據類型構成**，除了在Hue左側查看外，也可以用`DESC`語句查詢：

```sql
DESC table_name ;
```

其中，**col\_name**表示字段、**data\_type**表示字段的數據類型、**comment**為字段備註。

常見數據類型有：數值類型(numeric  Type)，時間類型(Date/Time Type)，字串符類型(string Type) 。具體以什麼類型儲存，一般會由資料庫工程師設計，對於數據分析師，知道字段屬於整數、浮點數、字符串或時間即可，若想進一步了解可參閱[官方文檔](https://cwiki.apache.org/confluence/display/Hive/LanguageManual+Types) 。\
\
