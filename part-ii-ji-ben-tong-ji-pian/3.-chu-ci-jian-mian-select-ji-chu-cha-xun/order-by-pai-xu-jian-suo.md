# ORDER BY排序檢索

SQL語句輸出一般是按照數據最初添加到表中的順序，為了明確的排序出檢索的數據，可以用`order by`進行排序；默認是升序(asc)排列(A-Z)， 用`DESC`可以轉為降序排列(Z-A)。

查詢訂單id、交易日期、及訂單原價，並依訂單日期(valid\_time)由**近到遠**排序：

```
select order_id, valid_time,original_price   
from dw.dws_order_d   
order by valid_time DESC  ;
```



多個字段排序，用,分開即可，例如先依交易日期由**近到遠**排序，再按照訂單原價**高到低**排序：

```
select order_id,valid_time,original_price    
from dw.dws_order_d     
order by valid_time DESC  , original_price DESC ;
```

``

`order by`是全局排序1，因此在數據量大的情况下，除了花費時間比較長，也會消耗大量計算資源，若數據工程師對平台做了mapReduce的限制，上述語法將無法執行，**要求必須`limit`限制返回行數**；若我們還是很需要全量的數據返回，可以在語句運行之前更改模式，語句如下：

```
set hive.mapred.mode=unstrict;
```

{% hint style="warning" %}
全局排序，就是在一個MapReduce程序產生的輸出文件中，所有的結果都是按照某個策略進行排序(例如降序或是升序)。 MapReduce只能保證一個分區內的數據是key有序的，一個分區對應一個reduce，因此只有一個reduce就保證了數據全局有序，但是這樣又不能用到Hadoop集群的優勢，就很費時間了。
{% endhint %}
