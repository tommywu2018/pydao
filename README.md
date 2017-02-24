# pydao
simple mysql access api based on sqlalchemy and pymysql

pymysql是一个纯python的mysql客户端包，它不依赖第三方c包，免除
了因安装导致的问题。

使用sqlalchemy on pymysql可以使返回的结果为类Dict类型，返回的
结果包括列名和列值，而不会像pymysql返回的纯粹tuple类型, 只有
列值。

另外sqlalchemy提供engine类，自动管理连接池，比直接使用pymysql的
connect更高效。

## TODO

1. 增加filter，可以指定返回哪些列

## 使用说明

```python
from pydao import Dao

dao = Dao(db, user, password, host)

# 插入一条记录
dao.insert_object('orders', {'time': '', 'oid': ''})

# 获取记录
dao.get_object('orders', {'name': ''})  # 返回匹配到的所有记录，返回的为list

# 更新记录
dao.update_object({'status': ''}, {'name': ''}, 'orders')  # 查找所有指定name的记录，更新status状态

# 删除记录
dao.delete_object('', 'name', 'orders')  # 删除name为''的记录

# 获取所有记录
dao.get_all_objects('orders')

# 删除所有记录
dao.delete_all_objects('orders')

# 判断记录是否存在
dao.is_exist({'name': ''}, 'orders')
```
