# IN與NOT IN過濾

同時選取多個值，可以用`in` ，且用逗號分隔，例如取出 sale\_channel為web官網跟移動端官網的訂單

```sql
select *
from dws_order_d 
where sale_channel in ('web官網','移動端官網') 
limit 100; 
```

\
