---
description: 比較運算
---

# 比較運算



數值比較：

```sql
select * from dws_order_d  
where original_price <= 1  ;
```

字符串比較：

```sql
select * from dws_order_d  
 where sale_channel='app商城' ;
```

時間比較：

```sql
select * from dws_order_d  
where valid_time = '2020-01-01 00:17:37' ;
```

{% hint style="info" %}
**如果日期寫到天，那麼默認的時分秒為00:00:00**

```sql
select * from dws_order_d  
where valid_time = '2020-01-01' ;
```
{% endhint %}

\
