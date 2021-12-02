# 聚合函數基本用法



| 聚合函數       | 解釋                       |
| ---------- | ------------------------ |
| count()    | 返回column中(非NULL)的行數      |
| sum()      | 返回column中所有值(非NULL)的求和結果 |
| avg()      | 返回column中所有值(非NULL)的平均值  |
| max()      | 返回column中(非NULL)最大值      |
| min()      | 返回column中(非NULL)最小值      |
| stddev()   | 反回column中所有值(非NULL)的標準差  |
| variance() | 反回column中所有值(非NULL)的變異數  |

{% hint style="info" %}
<mark style="color:blue;">**常見的坑，別踩到了！**</mark>&#x20;

NULL值不會參與到聚合函數的運算之中，也就是說，**所有聚合函數，會先把NULL排除在外再進行聚合計算，而不是當作0參與計算。**

<[_煩人的缺失數據與極端值_](../../../part-iii-shu-ju-yu-chu-li-pian/9.-fan-ren-de-que-shi-shu-ju-yu-ji-duan-zhi/)>這章將專門探討NULL的影響，目前先請當成已知



例如：有一個金額字段，裡面有3個值，分別是10、10、 null，那麼對他count是等於2(NULL不參與計算)、對他sum是20(NULL不參與計算)，對他avg是10。\

{% endhint %}



從訂單表中，計算三個指標，總訂單數(order\_cou)、總支付金額(pay\_ttl)跟平均支付金額(pay\_avg)，可以用以下查詢：

```sql
select       
    count(order_id) as order_cou,      
    sum(pay_amount) as pay_ttl,      
    avg(pay_amount) as pay_avg   
from dws_order_d    ;

```

