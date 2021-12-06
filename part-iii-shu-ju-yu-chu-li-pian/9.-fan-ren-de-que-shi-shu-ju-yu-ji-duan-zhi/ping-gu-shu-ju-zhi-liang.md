# 評估數據質量

清理數據時，首先要發現缺失數據，`count(column)`計算column中非NULL的行數，但`COUNT(*)`可以得到包含NULL在內的所有行數。因此可使用以下代碼校驗是否有缺失數據：

```sql
select count(*),count(id1),count(id2) from  dw.missing_value;
```

或是以下代碼，當等號成立返回trun，反之則為false：

```sql
select  
  count(id1)=count(*) as is_id1_no_null, -- id1是否有null,等號成立表示沒有
  count(id2)=count(*) as is_id2_no_null   -- id2是否有null,等號成立表示沒有
from dw.missing_value;
```

另一個問題是缺失的程度，以對其進行處理。例如，缺失數據佔較少的比例(<1%)，則刪除掉該數據；缺失數據佔較高比例(20%)，則利用平均值、或是業務典型值來填補。

> 缺失占比小到多小要剔除、缺失占比高到多高要填補，這個比例取決於業務性質；另填補方式也會因業務場景而有不同的考量，這部分屬於數據分析範圍，暫不展開介紹。

查詢字段的缺失值佔比，我們可以用以下查詢：

```sql
SELECT 
  1-(count(id1)/count(*)) as miss_perc_1 ,    
  1-(count(id2)/count(*)) as miss_perc_2
 from dw.missing_value;
```

如果空字符串，也被認為是屬於缺失數據要統計的話，可以使用控制函數實現，代碼如下：

```sql
select 
sum(case when id1 is NULL or trim(id1) = '' then 1 ELSE 0 end) / count(*) as miss_perc_1,
sum(case when id2 is NULL or id2 in('',' ') then 1 ELSE 0 end) / count(*) as miss_perc_2
from dw.missing_value;

```

