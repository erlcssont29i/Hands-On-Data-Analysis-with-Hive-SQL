# 單個檢索、多個檢索與\*符號

查詢訂單表中的訂單id：

```
select order_id from dw.dws_order_d ;
```

輸出如下：

多個檢索則用,隔開，例如查詢訂單id(order\_id)與訂單狀態(order\_state)：

```
select order_id,order_state from dw.dws_order_d ;
```

輸出如下：

把所有字段都列出來，則可以使用\*符號，雖然用起來很方便，但是**對查詢性能上會有影響，所以如果查詢語句複雜的話應盡量避免使用。**

```
select * from dw.dws_order_d ;
```

輸出如下：

* dw是庫名，如果查詢的表與當前使用數據庫一至，可以省略不寫
* SQL對大小寫不敏感 ，例如`select` ,`SELECT`, `Select` 是相同的；另空格會被忽略，也就是SQL語句可以寫長長一行，也可以分寫在多行。**為了閱讀方便，對於比較複雜的SQL語句建議寫成多行**。

```
SELECT   
    order_id,  
    order_state 
 FROM dw.dws_order_d ;
```

\
