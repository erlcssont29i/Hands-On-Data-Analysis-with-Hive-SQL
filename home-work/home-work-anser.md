# Home work Anser



**作業繳交規範：**

【作業標題】請依照此格式命名：\<HiveSQL>chX作業X

```
範例：<HiveSQL>_ch3_作業1
```

【繳交方式】

1. 直接貼上自己寫的代碼留言送出
2. 將代碼及返回結果截圖上傳

### Ch3 初次見面：SELECT基礎查詢&#x20;

\<HiveSQL\_ch3\_作業1>



### Ch4 初次見面：過濾你想要的數據

\<HiveSQL\_ch4\_作業1>



### Ch5 初次見面：過濾你想要的數據

\<HiveSQL\_ch5\_作業1>



```sql
select *,  
original_price-pay_amount as reduce_amount, 
(original_price-pay_amount)/original_price as reduce_rate 
 from dws_order_d order by reduce_amount desc        ;
```



### Ch6 初次見面：過濾你想要的數據

\<HiveSQL\_ch6\_作業1>

```sql
select 
   goods_id,
   count(order_id) as order_cou,
   count(distinct user_id) as user_cou ,
   max(original_price-pay_amount) as reduce_amount_max,
   avg(original_price-pay_amount) as reduce_amount_avg,
   max((original_price-pay_amount)/original_price) as reduce_rate_max,
   avg((original_price-pay_amount)/original_price) as reduce_rate_avg
 from dw.dws_order_d 
  where order_id not like'%test%' and (original_price<>0 and original_price is not null) 
  group by goods_id
   having order_cou >= 10000
   order by order_cou desc 
   ;
```

### Ch7 初次見面：過濾你想要的數據

\<HiveSQL\_ch7\_作業1>

```sql
SELECT 
count(order_id) as order_cou_ttl , 
count(if(city in ('10017','63','65','10003','10004'),order_id,null)) as order_cou_n,
count(if( city in('10005','66','10007','10008','10009'),order_id,null)) as order_cou_m,
count(if( city in ('Chiayi','67','64','10013'),order_id,null)) as order_cou_s,
avg(pay_amount) as pay_avg_ttl , 
avg(if(city in ('10017','63','65','10003','10004'),pay_amount,null)) as  pay_avg_n,
avg(if( city in ('10005','66','10007','10008','10009'),pay_amount,null)) as  pay_avg_m,
avg(if( city in ('Chiayi','67','64','10013'),pay_amount,null)) as  pay_avg_s
	from dw.dws_order_d 
 where order_id not like'%test%' 
   and (original_price <> 0 or original_price is not null )
 ;
```

### Ch8 初次見面：過濾你想要的數據

\<HiveSQL\_ch8\_作業1>

```sql
```

\<HiveSQL\_ch8\_作業2>

```
```

\<HiveSQL\_ch8\_作業3>

```
```

### Ch9 初次見面：過濾你想要的數據

\<HiveSQL\_ch9\_作業1>

```sql
```

### Ch10 初次見面：過濾你想要的數據

\<HiveSQL\_ch10\_作業1>

```
select *,  
original_price-pay_amount as reduce_amount, 
(original_price-pay_amount)/original_price as reduce_rate 
 from dws_order_d order by reduce_amount desc        ;
```

### Ch11 初次見面：過濾你想要的數據

\<HiveSQL\_ch11\_作業1>

```sql
SELECT
a.*,b.*,c.*,d.* 
FROM
(select * from dw.dws_order_d) a 
left join (select * from dw.dws_user_d) b ON a.user_id=b.user_id
left join (select * from dw.dws_mkt_act_d) c   ON a.ump_id=c.ump_id
left join (select distinct city_code,city from dw.dim_city) d  ON a.city=d.city_code
;
```

\<HiveSQL\_ch11\_作業2>

```sql
SELECT  
 a.*
FROM 
(select 'id'as id, * from dw.dws_order_d ) a 
join 
(select 
  'id'as id,
	percentile(cast(pay_amount*100 as int) , 0.01)/100 as op_01,
	percentile(cast(pay_amount*100 as int) , 0.99)/100 as op_99
 from dw.dws_order_d )  b ON a.id=b.id
 -- where a.pay_amount between b.op_01 and op_99 ; 
 where a.pay_amount > b.op_01 and a.pay_amount  < b.op_99 ; 
```

### Ch12 初次見面：過濾你想要的數據

\<HiveSQL\_ch12\_作業1>

```sql
SELECT
a.*,b.*,c.*,d.* 
FROM
(select * from dw.dws_order_d) a 
left join (select * from dw.dws_user_d) b ON a.user_id=b.user_id
left join (select * from dw.dws_mkt_act_d) c   ON a.ump_id=c.ump_id
left join (select distinct city_code,city from dw.dim_city) d  ON a.city=d.city_code
;
```

### Ch14 初次見面：過濾你想要的數據

\<HiveSQL\_ch14\_作業1>

```sql
SELECT
a.*,b.*,c.*,d.* 
FROM
(select * from dw.dws_order_d) a 
left join (select * from dw.dws_user_d) b ON a.user_id=b.user_id
left join (select * from dw.dws_mkt_act_d) c   ON a.ump_id=c.ump_id
left join (select distinct city_code,city from dw.dim_city) d  ON a.city=d.city_code
;
```



\<HiveSQL\_ch14\_作業2>

```sql
SELECT
a.*,b.*,c.*,d.* 
FROM
(select * from dw.dws_order_d) a 
left join (select * from dw.dws_user_d) b ON a.user_id=b.user_id
left join (select * from dw.dws_mkt_act_d) c   ON a.ump_id=c.ump_id
left join (select distinct city_code,city from dw.dim_city) d  ON a.city=d.city_code
;
```

