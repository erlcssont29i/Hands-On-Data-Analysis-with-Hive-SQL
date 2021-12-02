# 好用的取別名(alias)

通過四則運算產生的延伸字段，會默認取名為`_c1、_c2、_c3`，我們可以用`AS`對字段取新的別名(也可用空格取代`AS`，但為了代碼容易閱讀，通常不建議省略)；如果原字段覺得含義不清，也可以通過起別名(alias named)來更改。

我們把`original_price-pay_amount`命名為reduce\_amount：

```sql
select   
    order_id,  
    (original_price-pay_amount) as reduce_amount
from dws_order_d ;
```

{% hint style="info" %}
字段命名須符合以下的規則，若不符合命名規則，語句將報錯：

* 只能包括小寫字母(大寫字母會轉為小寫)、數字、下划線，
* 不可以下划線開頭
* 不可僅包含數字
{% endhint %}



