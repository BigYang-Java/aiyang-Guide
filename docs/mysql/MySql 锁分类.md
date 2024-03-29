# MySql 锁分类


MySQL中的锁主要分为以下几种：

 ** _共享锁和排他锁_ ** 

-   共享锁（读锁）：当一个事务为数据加上读锁之后，其他事务只能对该数据加读锁，而不能对数据加写锁，直到所有的读锁释放之后其他事务才能对其进行加持写锁。
-   排他锁（写锁）：当一个事务为数据加上写锁时，其他请求将不能再为数据加任何锁，直到该锁释放之后，其他事务才能对数据进行加锁。

 ** _行级锁和表级锁_ ** 

-   行级锁：例如在InnoDB存储引擎中使用，允许对数据库中的特定行进行锁定。
-   表级锁：例如在MyISAM存储引擎中使用，速度较快，但冲突较多。

 ** _记录锁、间隙锁、临键锁_ ** 

-   记录锁：直接作用于索引记录。
-   间隙锁：锁定一个范围，但不包括记录本身，用于防止幻读。
-   临键锁：锁定一个范围的两端记录。

 _ **意向共享锁和意向排他锁** _ 

-   意向共享锁：表明事务希望在稍后获取更具体的读锁。
-   意向排他锁：表明事务希望在稍后获取更具体的写锁。

以上就是MySQL中的主要几种锁类型，每种类型都有其特定的用途和适用场景。

  

原文地址：[MySql 锁分类](https://zhuanlan.zhihu.com/p/673515816) 


