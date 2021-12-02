# DISTINCT排除重複

`distinct`可以排除字段中重複的值，例如，想了解訂單狀態(order\_state)有哪幾類？

語句如下：

```sql
select distinct order_state from dw.dws_order_d ;
```

對多個字段去重，也是用,隔開，例如想了解不同銷售渠道(sale\_channel)有哪些訂單狀態(order\_state)，查語句如下：

```sql
select distinct order_state,sale_channel from dw.dws_order_d ;
```

