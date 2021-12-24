# Home work Anser

{% hint style="info" %}
* 每章節的作業請**務必經過思考並繳交**，勿直接看答案，否則學習效果將打(骨)折
* 解法不唯一，以下答案僅供參考
{% endhint %}

**作業繳交規範：**

【作業標題】請依照此格式命名：\<HiveSQL>chX作業X

```
範例：<HiveSQL>_ch3_作業1
```

【繳交方式】

1. 直接貼上自己寫的代碼留言送出
2. 將代碼及返回結果截圖上傳



### Ch3 初次見面：SELECT基礎查詢&#x20;

\<HiveSQL\_ch3\_作業1>&#x20;



### Ch4 過濾你想要的數據

\<HiveSQL\_ch4\_作業1>



```sql
select 
    order_id,
    original_price,
    pay_amount,
    sale_channel 
from dw.dws_order_d
where sale_channel ='web官網'
and (order_id like'%test%' OR original_price=0 OR original_price is null  )
;
```

###

### Ch5 生成新的字段-字段運算

\<HiveSQL\_ch5\_作業1>



```sql
select *,  
 original_price-pay_amount as reduce_amount, 
 (original_price-pay_amount)/original_price as reduce_rate 
 from dws_order_d order by reduce_amount desc   
 ;
```



### Ch6 最常見的分析問題：匯總與分組

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

###

### Ch7 好用的CASE WHEN與IF

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

###

### Ch8 初次見面：用函數高效的處理數據

\<HiveSQL\_ch8\_作業1>



```sql
SELECT 
substr(valid_time,1,7) as month,
count(order_id) as order_cou_ttl , 
count(if(city in ('10017','63','65','10003','10004'),order_id,null)) as order_cou_n,
count(if( city in('10005','66','10007','10008','10009'),order_id,null)) as order_cou_m,
count(if( city in ('Chiayi','67','64','10013'),order_id,null)) as order_cou_s,
round(avg(pay_amount),2) as pay_avg_ttl , 
round(avg(if(city in ('10017','63','65','10003','10004'),pay_amount,null)),2) as  pay_avg_n,
round(avg(if( city in ('10005','66','10007','10008','10009'),pay_amount,null)),2) as  pay_avg_m,
round(avg(if( city in ('Chiayi','67','64','10013'),pay_amount,null)),2) as  pay_avg_s
	from dw.dws_order_d 
 where order_id not like'%test%' and (original_price<>0 or original_price is not null)
  and substr(valid_time,1,7) between substr(add_months(CURRENT_TIMESTAMP,-12),1,7) and substr(add_months(CURRENT_TIMESTAMP,-1),1,7)
  group by substr(valid_time,1,7)
 ;
```



\<HiveSQL\_ch8\_作業2>



```sql
select 
-- user_id,
	substr(user_name,1,1) as fname,
	case when length(user_name)=2 then  substr(user_name,-1,1)
	when length(user_name)in (3,4) then substr(user_name,-2,2) end as sname, 
--  split(age,'-|\\+'),
--  split(age,'-|\\+')[0] as age_min,
--  if(split(age,'-|\\+')[1] ='' ,85 ,split(age,'-|\\+')[1])  as age_max , 
  (split(age,'-|\\+')[0]+
  if(split(age,'-|\\+')[1] ='' ,85 ,split(age,'-|\\+')[1]) )/2 as avg_age,
   --   ((replace(split(age,'-')[0],'+','')) + if((split(age,'-')[1]) is null,85,split(age,'-')[1])) /2 
     -- 	as avg_ag
  concat_ws('-',substr(mobile,1,4),substr(mobile,5,3),'***') as mobile
from dws_user_d 
 -- where user_id in ('1018934','1024010') 
 ; 
```



\<HiveSQL\_ch8\_作業3>



```sql
select 
user_id,
-- max(substr(valid_time,1,10)), 
datediff(current_date,max(substr(valid_time,1,10))) as r ,
count(distinct order_id) as f,
sum(pay_amount) as m
from dw.dws_order_d
where substr(valid_time,1,10)<current_date
group by user_id
;
```

###

### Ch9 煩人的缺失數據與極端值

\<HiveSQL\_ch9\_作業1>



```sql
```

###

### Ch10 實現多表查詢：子查詢

\<HiveSQL\_ch10\_作業1>



```sql
-- step 1: 
SELECT
  percentile(cast(r as int), 0.5) as r_mid,
  percentile(cast(f as int), 0.5) as f_mid,
  percentile(cast(m as int), 0.5) as m_mid
FROM
(select
user_id,
min(datediff(current_date, substr(valid_time, 1, 10))) as r,
count(order_id) as f,
sum(pay_amount) as m
from dw.dws_order_d
where substr(valid_time, 1, 10) < current_date
GROUP BY user_id) as rfm
;
 -- ** this query's result: r_mind=241, r_mid=1, m_mid=1596

-- step 2:
SELECT
    user_id,
    Recency,
    Frequency,
    Monetary,
    if(Recency < 241, '高', '低') as r_Level,
    if(Frequency > 1, '高', '低') as f_Level,
    if(Monetary > 1596, '高', '低') as m_Level
FROM
(select
user_id,
min(datediff(current_date, substr(valid_time, 1, 10))) as Recency,
count(order_id) as Frequency,
sum(pay_amount) as Monetary
from dw.dws_order_d
where substr(valid_time, 1, 10) < current_date
GROUP BY user_id) as rf
```

###

### Ch11 利用JOIN實現表的橫向連接

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

###

### Ch12 利用UNION實現表的縱向連接

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

###

### Ch14 強大的窗口函數

\<HiveSQL\_ch14\_作業1>



```sql
select 
user_id,
case when datediff(log_day,date2)=1 then 'y' else 'n' end as  log2day ,
case when datediff(log_day,date3)=2 then 'y' else 'n' end as  log3day ,
case when datediff(log_day,date4)=3 then 'y' else 'n' end as  log4day ,
case when datediff(log_day,date5)=4 then 'y' else 'n' end as  log5day ,
case when datediff(log_day,date6)=5 then 'y' else 'n' end as  log6day 
from
(select a.*,row_number()over(partition by user_id order by log_day desc  ) as rn
from 
(select user_id ,substr(log_time,1,10) as log_day,
 	 lead(substr(log_time,1,10),1) over(partition by user_id order by substr(log_time,1,10) desc ) as date2,
 	lead(substr(log_time,1,10),2) over(partition by user_id order by substr(log_time,1,10) desc ) as date3 ,
 	lead(substr(log_time,1,10),3) over(partition by user_id order by substr(log_time,1,10) desc ) as date4,
 	lead(substr(log_time,1,10),4) over(partition by user_id order by substr(log_time,1,10) desc ) as date5,
  lead(substr(log_time,1,10),5) over(partition by user_id order by substr(log_time,1,10) desc ) as date6
 	from default.user_login 
 		group by user_id,substr(log_time,1,10) ) a  ) b where rn=1
 		;
```

