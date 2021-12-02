# 取別名後如何排序

在對字段取了別名的情況下，要**以別名為排序的對象**，原因**涉及**[**hive語句執行順序**](../6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/hive-yu-ju-de-zhi-hang-shun-xu.md)**。**

例如，將`original_price`取別名為`o_price`，但仍以`original_price`為排序對象，顯示如下錯誤訊息：

![](https://tva1.sinaimg.cn/large/008eGmZEgy1gpepcp5kcuj31c60fmjtw.jpg)

\
