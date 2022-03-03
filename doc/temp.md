
# temp

需求如下:

1. 批量更新某个字段的值 = 另外一张表的某个字段的值

分析如下:

查询很容易,直接连表查询即可.
那么 用到 update 字段如何使用.

查询的语法如下:
```sql

SELECT product_snapshot_id,  saler_id , nft_product_snapshot.user_id as 'saler_id22'
from nft_trade_order_product 
LEFT JOIN nft_product_snapshot
on nft_trade_order_product.product_snapshot_id = nft_product_snapshot.id
where saler_id = '';

```

那么更新如下做:
```sql

update a
LEFT JOIN b
on a.id = b.id
set a.saler_id = b.user_id
where a.id = b.id
```

注意语法形式.
