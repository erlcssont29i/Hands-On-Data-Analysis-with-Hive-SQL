# Hive語句的執行順序

`order by`的字段一定要使用別名，`group by` 不能用別名，為什麼？原因涉及Hive-SQL語句執行的順序，其執行順序跟我們代碼寫的順序是不同的。

代碼寫的順序：

```sql
select ... from... where.... group by... having... order by...limit
```

代碼執行的順序：

```sql
from... where...group by... having...select... distinct ... order by...limit 
```

hive基于MapReduce，所以他的執行順序决定了hive語句的執行順序，可以再任意語句前，加上`explain`查看，簡單說明如下：

**Map階段：**

1. 執行from，進行表的查找與加載
2. 執行where過濾，進行條件過濾與篩選
3. 執行select査詢：進行輸出項的篩選
4. 執行group by分組：描述了分組後需要計算的函數
5. map端檔合併：map端本地溢出寫檔案的合併操作，每個map最終形成一個暫存檔案。

**Reduce階段：**

1. group by：對map端發送過來的數據進行分組並進行計算。
2. select：最後過濾column用於輸出結果
3. limit排序後進行結果輸出到HDFS

