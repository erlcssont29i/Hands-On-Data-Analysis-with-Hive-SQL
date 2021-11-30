# SELECT起手式與語句順序

下面是一段SQL的完整語句，查詢的各種操作都從這些語句組合而來。

```
select ...  
 from ...    
  where ....      
   group by ..         
    having ...           
     order by ...             
      limit ...          ;
```

其中：

* `select ... from ...`表示從table中取出某個字段
* `where` 為限制條件，可理解為取子數據
* `Group by` 為分組
* `having`為分組後的限制條件
* `order by`為排序
* `limit`為限制返回結果的行數



剛開始學習時，最好就對語句的順序有概念。因為一個查詢可能只會用到部分語句，但若語句沒按順序，執行會出現報錯。

