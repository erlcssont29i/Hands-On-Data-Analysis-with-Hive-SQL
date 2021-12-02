# BETWEEN...AND

`between...and...`主要用來篩選數值類型跟時間類型的字段 (字符串其實也可以，但需要了解Hive怎麼對文字的排序方式，不建議使用)。須**由小至大**；另外，hive中的`between...and...`是**包括**邊界值的、`not between...and...`則**不包括**邊界值。



BETWEEN...AND... 數值

```sql
select *
from dws_order_d  
where original_price between 1.11 and 1.95  
order by original_price ;  
```

```sql
select * 
from dws_order_d  
where original_price not between 1.11 and 1.95  
order by original_price ;
```

從返回結果可以看出不包含1.1，驗證`not between...and...`**不包括**邊界值



BETWEEN...AND... 時間

```sql
select *
from dws_order_d  
where valid_time between '2020-01-01' and '2020-01-02' 
 order by valid_time desc 
  limit 10 ;
```



{% hint style="info" %}
前面提過，**如果日期是到天的，那麼默認的時分秒為00:00:00**，因此在此例中，and 後的日期為2020 年1 月2日，就等價於2020-01-02 00:00:00 ，那麼2020-01-02 00:30:29 的數據就查不到了。

**如果要查到2020-01-02這一整天的數據，那麼在取值的時候需要加1天，即BETWE '2020-01-01' AND '2020-01-03'，這樣返回的就是1月1日(含)到1月2日(含)的所有數據了。**

然而實務上，利用**時間處理函數**進行處理會是更常見的做法，在<[_用函數高效的處理數據_](../../part-iii-shu-ju-yu-chu-li-pian/8.-yong-han-shu-gao-xiao-chu-li-shu-ju.md)>的章節將詳細介紹。
{% endhint %}

