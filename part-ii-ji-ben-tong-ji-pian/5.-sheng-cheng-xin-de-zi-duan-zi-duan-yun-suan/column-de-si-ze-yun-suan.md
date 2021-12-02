# Column的四則運算

**數值類型**的字段，可以進行加、減、乘、除的四則運算，運算優先級跟數學運算的優先級是一樣的，即**先乘除後加減**

| 運算符  | 描述   |
| ---- | ---- |
| A+B  | A加B  |
| A-B  | A減B  |
| A\*B | A乘以B |
| A/B  | A除以B |

```
select 1+2 ,    
    1-2 ,    
    1*2 ,    
    1/2 ,    
    1+2*2 ,    
    (1+2)*2,    
    (1+2)/(1-2) ;
```

返回如下：

![](https://tva1.sinaimg.cn/large/008eGmZEly1gpc7orx8a1j30th0b374l.jpg)

訂單表中的金額有原價(original\_price)和支付金額(pay\_amount)，我們將兩字段相減，獲得**折扣金額**：

```
select   
    order_id,  
    valid_time, 
    original_price,  
    pay_amount,  
    original_price-pay_amount
from dws_order_d 
where valid_time between '2020-06-01' and '2020-06-02'
limit 10 ;
```

\
