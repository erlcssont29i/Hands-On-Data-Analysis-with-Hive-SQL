# Table of contents

## Introduction

* [About This Book](README.md)
* [Why Learning Hive SQL](introduction/why-learning-hive-sql.md)

## Part I-工具準備與基礎知識

* [About Part I](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/about-part-i.md)
* [1.大數據基本概念：認識大數據](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/1.-da-shu-ju-ji-ben-gai-nian-ren-shi-da-shu-ju/README.md)
  * [什麼是大數據](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/1.-da-shu-ju-ji-ben-gai-nian-ren-shi-da-shu-ju/shi-mo-shi-da-shu-ju.md)
  * [認識開發環境：Hadoop與Hive](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/1.-da-shu-ju-ji-ben-gai-nian-ren-shi-da-shu-ju/ren-shi-kai-fa-huan-jing-hadoop-yu-hive.md)
  * [Hive與關聯式資料庫的區別](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/1.-da-shu-ju-ji-ben-gai-nian-ren-shi-da-shu-ju/hive-yu-guan-lian-shi-zi-liao-ku-de-qu-bie.md)
  * [認識Hue與Table](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/1.-da-shu-ju-ji-ben-gai-nian-ren-shi-da-shu-ju/ren-shi-hue-yu-table.md)
* [2.大數據環境安裝與數據導入](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/2.-da-shu-ju-huan-jing-an-zhuang-yu-shu-ju-dao-ru/README.md)
  * [Hadoop環境安裝](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/2.-da-shu-ju-huan-jing-an-zhuang-yu-shu-ju-dao-ru/hadoop-huan-jing-an-zhuang.md)
  * [課程數據模型與導入](partigong-ju-zhun-bei-yu-ji-chu-zhi-shi/2.-da-shu-ju-huan-jing-an-zhuang-yu-shu-ju-dao-ru/ke-cheng-shu-ju-mo-xing-yu-dao-ru.md)

## Part II-基本統計篇

* [About Part II](part-ii-ji-ben-tong-ji-pian/about-part-ii.md)
* [3.初次見面：SELECT基礎查詢](part-ii-ji-ben-tong-ji-pian/3.-chu-ci-jian-mian-select-ji-chu-cha-xun/README.md)
  * [SELECT起手式與語句順序](part-ii-ji-ben-tong-ji-pian/3.-chu-ci-jian-mian-select-ji-chu-cha-xun/select-qi-shou-shi-yu-yu-ju-shun-xu.md)
  * [單個檢索、多個檢索與\*符號](part-ii-ji-ben-tong-ji-pian/3.-chu-ci-jian-mian-select-ji-chu-cha-xun/dan-ge-jian-suo-duo-ge-jian-suo-yu-fu-hao.md)
  * [LIMIT 限制返回行數](part-ii-ji-ben-tong-ji-pian/3.-chu-ci-jian-mian-select-ji-chu-cha-xun/limit-xian-zhi-fan-hui-hang-shu.md)
  * [ORDER BY排序檢索](part-ii-ji-ben-tong-ji-pian/3.-chu-ci-jian-mian-select-ji-chu-cha-xun/order-by-pai-xu-jian-suo.md)
  * [DISTINCT排除重複](part-ii-ji-ben-tong-ji-pian/3.-chu-ci-jian-mian-select-ji-chu-cha-xun/distinct-pai-chu-zhong-fu.md)
* [4.過濾你想要的數據](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/README.md)
  * [比較運算](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/bi-jiao-yun-suan.md)
  * [BETWEEN...AND](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/between...and.md)
  * [IN與NOT IN過濾](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/in-yu-not-in-guo-lv.md)
  * [模糊查詢：LIKE與通配符(％)](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/mo-hu-cha-xun-like-yu-tong-pei-fu.md)
  * [NULL的過濾](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/null-de-guo-lv.md)
  * [多過濾條件组合](part-ii-ji-ben-tong-ji-pian/4.-guo-lv-ni-xiang-yao-de-shu-ju/duo-guo-lv-tiao-jian-zu-he.md)
* [5.生成新的字段-字段運算](part-ii-ji-ben-tong-ji-pian/5.-sheng-cheng-xin-de-zi-duan-zi-duan-yun-suan/README.md)
  * [Column的四則運算](part-ii-ji-ben-tong-ji-pian/5.-sheng-cheng-xin-de-zi-duan-zi-duan-yun-suan/column-de-si-ze-yun-suan.md)
  * [好用的取別名(alias)](part-ii-ji-ben-tong-ji-pian/5.-sheng-cheng-xin-de-zi-duan-zi-duan-yun-suan/hao-yong-de-qu-bie-ming-alias.md)
  * [取別名後如何排序](part-ii-ji-ben-tong-ji-pian/5.-sheng-cheng-xin-de-zi-duan-zi-duan-yun-suan/qu-bie-ming-hou-ru-he-pai-xu.md)
  * [代碼註釋](part-ii-ji-ben-tong-ji-pian/5.-sheng-cheng-xin-de-zi-duan-zi-duan-yun-suan/dai-ma-zhu-shi.md)
* [6.最常見的分析問題：匯總與分組](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/README.md)
  * [聚合函數基本用法](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/ju-he-han-shu-ji-ben-yong-fa/README.md)
  * [GROUP BY 指定分組對象](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/group-by-zhi-ding-fen-zu-dui-xiang.md)
  * [DISTINCT與聚合函數的配合](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/distinct-yu-ju-he-han-shu-de-pei-he.md)
  * [HAVING過濾分組後的數據](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/having-guo-lv-fen-zu-hou-de-shu-ju.md)
  * [GROUP BY 去重](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/group-by-qu-zhong.md)
  * [Hive語句的執行順序](part-ii-ji-ben-tong-ji-pian/6.-zui-chang-jian-de-fen-xi-wen-ti-hui-zong-yu-fen-zu/ju-he-han-shu-ji-ben-yong-fa/hive-yu-ju-de-zhi-hang-shun-xu.md)

## Part III-數據預處理篇

* [About Part III](part-iii-shu-ju-yu-chu-li-pian/about-part-iii.md)
* [7.好用的CASE與WHEN IF](part-iii-shu-ju-yu-chu-li-pian/7.-hao-yong-de-case-yu-when-if/README.md)
  * [CASE WHEN函數](part-iii-shu-ju-yu-chu-li-pian/7.-hao-yong-de-case-yu-when-if/case-when-han-shu.md)
  * [IF函數](part-iii-shu-ju-yu-chu-li-pian/7.-hao-yong-de-case-yu-when-if/if-han-shu.md)
* [8.用函數高效處理數據](part-iii-shu-ju-yu-chu-li-pian/8.-yong-han-shu-gao-xiao-chu-li-shu-ju/README.md)
  * [常用數值處理函數](part-iii-shu-ju-yu-chu-li-pian/8.-yong-han-shu-gao-xiao-chu-li-shu-ju/chang-yong-shu-zhi-chu-li-han-shu.md)
  * [常用時間處理函數](part-iii-shu-ju-yu-chu-li-pian/8.-yong-han-shu-gao-xiao-chu-li-shu-ju/chang-yong-shi-jian-chu-li-han-shu.md)
  * [常用字符串處理函數](part-iii-shu-ju-yu-chu-li-pian/8.-yong-han-shu-gao-xiao-chu-li-shu-ju/chang-yong-zi-fu-chuan-chu-li-han-shu.md)
* [9.煩人的缺失數據與極端值](part-iii-shu-ju-yu-chu-li-pian/9.-fan-ren-de-que-shi-shu-ju-yu-ji-duan-zhi/README.md)
  * [評估數據質量](part-iii-shu-ju-yu-chu-li-pian/9.-fan-ren-de-que-shi-shu-ju-yu-ji-duan-zhi/ping-gu-shu-ju-zhi-liang.md)
  * [缺失值對聚合函數及算術運算的影響](part-iii-shu-ju-yu-chu-li-pian/9.-fan-ren-de-que-shi-shu-ju-yu-ji-duan-zhi/que-shi-zhi-dui-ju-he-han-shu-ji-suan-shu-yun-suan-de-ying-xiang.md)
  * [缺失值的處理方法](part-iii-shu-ju-yu-chu-li-pian/9.-fan-ren-de-que-shi-shu-ju-yu-ji-duan-zhi/que-shi-zhi-de-chu-li-fang-fa.md)
  * [查找極端值](part-iii-shu-ju-yu-chu-li-pian/9.-fan-ren-de-que-shi-shu-ju-yu-ji-duan-zhi/cha-zhao-ji-duan-zhi.md)

## Part IV-數據分析進階

* [About Part IV](part-iv-shu-ju-fen-xi-jin-jie/about-part-iv.md)
* [10.實現多表查詢：子查詢](part-iv-shu-ju-fen-xi-jin-jie/10.-shi-xian-duo-biao-cha-xun-zi-cha-xun.md)
* [11.利用JOIN實現表的橫向連接](part-iv-shu-ju-fen-xi-jin-jie/11.-shi-xian-duo-biao-cha-xun-li-yong-join-shi-xian-biao-de-heng-xiang-lian-jie.md)
* [12.利用UNION實現表的縱向連接](part-iv-shu-ju-fen-xi-jin-jie/12.-shi-xian-duo-biao-cha-xun-li-yong-union-shi-xian-biao-de-zong-xiang-lian-jie.md)
* [13.改變表結構：行列互轉](part-iv-shu-ju-fen-xi-jin-jie/13.-gai-bian-biao-jie-gou-hang-lie-hu-zhuan.md)
* [14.強大的窗口函數](part-iv-shu-ju-fen-xi-jin-jie/14.-qiang-da-de-chuang-kou-han-shu.md)
* [15.庫、表的操作](part-iv-shu-ju-fen-xi-jin-jie/15.-ku-biao-de-cao-zuo.md)
