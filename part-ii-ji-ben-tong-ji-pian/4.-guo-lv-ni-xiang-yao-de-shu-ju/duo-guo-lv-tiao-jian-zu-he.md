# 多過濾條件组合

當過濾條件不止一條時，我們可以用`AND` 、`OR`來建立多條件的組合關係。用`AND`連接即表示必須所有條件同時滿足；用`OR`連接即至少一個條件滿足即可；如果用數學表達，`AND`就是交集 、`OR`就是聯集。

前面查詢過 sale\_channel為web官網跟移動端官網的訂單，以下的語句查詢，也可得到相同的結果。

```sql
select *
from dws_order_d 
where sale_channel='web官網' or sale_channel='移動端官網' ; 
```

**當and、or同時出現，Hive會以and為優先**。使用()將條件區分開，Hive就會優先執行括號內的條件語句。一來可以避免邏輯錯誤，二來邏輯會更清晰。

\
