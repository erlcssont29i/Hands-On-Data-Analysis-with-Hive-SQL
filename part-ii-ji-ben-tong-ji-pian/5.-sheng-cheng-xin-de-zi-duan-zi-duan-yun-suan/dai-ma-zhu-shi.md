# 代碼註釋

在Hive，使用 `--` 之後的文字將不被執行，方便對代碼進行註釋。

```
-- 註釋不被執行
SELECT 
 order_id,  
 original_price as o_price, -- 原價  
 pay_amount as p_price, -- 支付金額  
 (original_price-pay_amount) as reduce_amount --折扣金額,原價 - 支付金額
FROM dws_order_d 
  where valid_time between '2020-06-01' and '2020-06-02'  
   order by reduce_amount desc,    o_price desc  -- 用別名排序 
 limit 10 ;
```

\
