# NULL的過濾

**NULL(空值) 和 ''(空字符串)** 是兩個不同的東西。空值的字段在hive中會轉化為NULL，而空字符串是長度為0的字符串。

NULL時，則要使用`is NULL` (或是`is not NULL`) 篩選

```
select *
from dws_order_d 
where original_price is null ;
```

空字符串的查詢方式如下：

```
select *
from dws_order_d 
where order_id ='' ;
```

但若hive底層保存的NULL是個字符串，想要過濾掉NULL值，用`is not null`反而則無效：

```
select *
from dws_order_d 
 where  original_price = 'NULL' ;
```

\
