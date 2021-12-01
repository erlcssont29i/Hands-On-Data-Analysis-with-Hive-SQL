---
description: 比較運算
---

# 比較運算



* 數值比較：

```
select order_id,valid_time,original_price,pay_amount,order_state,sale_channel,city from dws_order_d  where original_price <= 1    order by original_price desc    limit 100;
```

* 字符串比較：

```
select order_id,valid_time,original_price,pay_amount,order_state,sale_channel,city from dws_order_d   where sale_channel='app商城'    order by original_price desc    limit 100;
```

* 時間比較：

```
select order_id,valid_time,original_price,pay_amount,order_state,sale_channel,city from dws_order_d  where valid_time = '2020-01-01 00:17:37'  order by valid_time desc  limit 100;
```



**如果日期是到天的，那麼默認的時分秒為00:00:00**

```
select order_id,valid_time,original_price,pay_amount,order_state,sale_channel,city from dws_order_d  where valid_time = '2020-01-01'  order by valid_time desc  limit 100;
```

\
