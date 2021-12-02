# LIMIT 限制返回行數

前面的查詢語句會返回所有數據，但有時候我們只是要確認一下表中的數據內容，可用`limit`限制返回的行數，例如返回5條數據：

```sql
SELECT   
    order_id,  
    order_state 
FROM dw.dws_order_d  
 limit 5;
```





