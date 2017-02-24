# pydao
simple mysql access api based on sqlalchemy and pymysql

pymysql是一个纯python的mysql客户端包，它不依赖第三方c包，免除
了因安装导致的问题。

使用sqlalchemy on pymysql可以使返回的结果为类Dict类型，返回的
结果包括列名和列值，而不会像pymysql返回的纯粹tuple类型, 只有
列值。

另外sqlalchemy提供engine类，自动管理连接池，比直接使用pymysql的
connect更高效。
